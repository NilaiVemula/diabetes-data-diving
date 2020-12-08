Linear Regression Model
================
Nilai Vemula
December 7, 2020

# Loading in Data

This notebook will be focused on building a predictive model from the
dataset. The response variable is class, and all other variables are
predictors. All predictors are categorical except for Age which is a
ordinal variable.

``` r
require(tidyverse)
```

    ## Loading required package: tidyverse

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.2     v purrr   0.3.4
    ## v tibble  3.0.1     v dplyr   1.0.0
    ## v tidyr   1.1.2     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.5.0

    ## Warning: package 'tidyr' was built under R version 4.0.3

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
data <- read_csv("../data/clean_numeric_data.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   Age = col_double(),
    ##   Gender = col_double(),
    ##   Polyuria = col_double(),
    ##   Polydipsia = col_double(),
    ##   sudden.weight.loss = col_double(),
    ##   weakness = col_double(),
    ##   Polyphagia = col_double(),
    ##   Genital.thrush = col_double(),
    ##   visual.blurring = col_double(),
    ##   Itching = col_double(),
    ##   Irritability = col_double(),
    ##   delayed.healing = col_double(),
    ##   partial.paresis = col_double(),
    ##   muscle.stiffness = col_double(),
    ##   Alopecia = col_double(),
    ##   Obesity = col_double(),
    ##   class = col_double()
    ## )

``` r
data
```

    ## # A tibble: 520 x 17
    ##      Age Gender Polyuria Polydipsia sudden.weight.l~ weakness Polyphagia
    ##    <dbl>  <dbl>    <dbl>      <dbl>            <dbl>    <dbl>      <dbl>
    ##  1    40      0        0          1                0        1          0
    ##  2    58      0        0          0                0        1          0
    ##  3    41      0        1          0                0        1          1
    ##  4    45      0        0          0                1        1          1
    ##  5    60      0        1          1                1        1          1
    ##  6    55      0        1          1                0        1          1
    ##  7    57      0        1          1                0        1          1
    ##  8    66      0        1          1                1        1          0
    ##  9    67      0        1          1                0        1          1
    ## 10    70      0        0          1                1        1          1
    ## # ... with 510 more rows, and 10 more variables: Genital.thrush <dbl>,
    ## #   visual.blurring <dbl>, Itching <dbl>, Irritability <dbl>,
    ## #   delayed.healing <dbl>, partial.paresis <dbl>, muscle.stiffness <dbl>,
    ## #   Alopecia <dbl>, Obesity <dbl>, class <dbl>

# chi square feature selection

These are the results from the chi-square feature selection process:

Polyuria 227.86583895  
Polydipsia 216.17163270  
Gender 103.03685928  
sudden weight loss 97.29630348  
partial paresis 95.38762744

# Building the linear model

``` r
# building the linear model
model <- lm(class ~ Age + Gender + Polyuria + Polydipsia + sudden.weight.loss + partial.paresis, data=data)

summary(model)
```

    ## 
    ## Call:
    ## lm(formula = class ~ Age + Gender + Polyuria + Polydipsia + sudden.weight.loss + 
    ##     partial.paresis, data = data)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -0.6059 -0.1747 -0.1662  0.1614  0.8311 
    ## 
    ## Coefficients:
    ##                      Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)         0.1885380  0.0580208   3.249  0.00123 ** 
    ## Age                -0.0003632  0.0011812  -0.307  0.75864    
    ## Gender              0.2190474  0.0314266   6.970 9.77e-12 ***
    ## Polyuria            0.3623175  0.0367050   9.871  < 2e-16 ***
    ## Polydipsia          0.3052143  0.0361974   8.432 3.47e-16 ***
    ## sudden.weight.loss  0.0710132  0.0319390   2.223  0.02662 *  
    ## partial.paresis     0.0400450  0.0330831   1.210  0.22667    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.3113 on 513 degrees of freedom
    ## Multiple R-squared:  0.596,  Adjusted R-squared:  0.5913 
    ## F-statistic: 126.1 on 6 and 513 DF,  p-value: < 2.2e-16

MSPE:

``` r
mean(model$residual^2)
```

    ## [1] 0.09561477

\(R^2\):

``` r
summary(model)$r.squared 
```

    ## [1] 0.5960276

Residual Plot:

``` r
mod_results <- data.frame(observed = data$class, predicted = model$fitted.values, residual = model$residuals)
head(mod_results)
```

    ##   observed predicted   residual
    ## 1        1 0.4792263 0.52077365
    ## 2        1 0.2075204 0.79247964
    ## 3        1 0.5359663 0.46403365
    ## 4        1 0.2432095 0.75679047
    ## 5        1 0.9453391 0.05466093
    ## 6        1 0.8360966 0.16390344

``` r
ggplot(mod_results, aes(y = residual, x = predicted)) + 
    geom_point() + 
    geom_hline(yintercept = 0) +
      theme_bw() +
  labs(title="Residual Plot", x="Predicted", y="Residual") +
  theme(plot.title = element_text(hjust = 0.5)) +
  theme(plot.background = element_rect(fill = '#f2f2f2', colour = '#f2f2f2')) +
  theme(panel.background = element_rect(fill = '#f2f2f2', colour = '#f2f2f2'))
```

![](linear_model_files/figure-gfm/residual-1.png)<!-- -->

``` r
ggsave("../plots/residual_plot.png", dpi = 1200, width = 4, height = 4, units = "in")
```

Q-Q Plot:

``` r
ggplot(mod_results, aes(sample = residual)) + 
    geom_qq()+
  geom_qq_line() +
  theme_bw() +
  labs(title="Q-Q Plot", x="Theoretical Quantile", y="Sample Quantile") +
  theme(plot.title = element_text(hjust = 0.5)) +
  theme(plot.background = element_rect(fill = '#f2f2f2', colour = '#f2f2f2')) +
  theme(panel.background = element_rect(fill = '#f2f2f2', colour = '#f2f2f2'))
```

![](linear_model_files/figure-gfm/qq-1.png)<!-- -->

``` r
ggsave("../plots/qq_plot.png", dpi = 1200, width = 4, height = 4, units = "in")
```

``` r
mean_res <- mean(mod_results$residual)
sd_res <- sd(mod_results$residual)
print(c(mean_res, sd_res))
```

    ## [1] -2.469760e-17  3.095141e-01
