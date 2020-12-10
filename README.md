# Diabetes Data Diving

## Description

**MATH 2820L Final Project** by Nilai Vemula, Anvitha Kosuraju, and Sithara Samudrala

This project features analysis of a [dataset](https://archive.ics.uci.edu/ml/datasets/Early+stage+diabetes+risk+prediction+dataset.) from the UCI Machine Learning Repository about diabetes. Our [project proposal](proposal.md) includes information about how we want to analyze and model our data. Additionally, this [write-up](writeup.md) documents our process and findings, and our [final presentation](presentation.pdf) shows this information in slides.

**Write-up**: [PDF](writeup.pdf) [Markdown](writeup.md)


## Notebooks

The code for this project can be found in the following Rmarkdown notebooks:

- [Exploratory Data Analysis](notebooks/exploratory_data_analysis.Rmd)
- [Linear Model](notebooks/linear_model.Rmd) (Markdown with output [here](notebooks/linear_model.md))
- [Random Forest Model](notebooks/random_forest.Rmd) (Markdown with output [here](notebooks/random_forest.md))

A bonus Jupyter Notebook containing more advanced modeling of our data can be found [here](python/model_building.ipynb).

### Reproducability

The code in these notebooks can be downloaded by cloning this repository using:

```{bash}
git clone https://github.com/NilaiVemula/diabetes-data-diving.git
```

Then, an R environment can be set-up using [`renv`](https://cran.r-project.org/web/packages/renv/index.html). Once this project is lauched, `renv` should automatically set up an enironment at which point you can run the following code in R to restore the project library:

```{r}
renv::restore()
```

In order to run the Jupyter Notebook you will need to set up a Python virtual environment using the following code:

```{bash}
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt
```

