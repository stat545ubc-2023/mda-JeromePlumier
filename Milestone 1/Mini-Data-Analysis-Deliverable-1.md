Mini Data-Analysis Deliverable 1
================

- [Welcome to your (maybe) first-ever data analysis
  project!](#welcome-to-your-maybe-first-ever-data-analysis-project)
- [Instructions](#instructions)
  - [For Both Milestones](#for-both-milestones)
  - [For Milestone 1](#for-milestone-1)
- [Learning Objectives](#learning-objectives)
- [Task 1: Choose your favorite
  dataset](#task-1-choose-your-favorite-dataset)
  - [1.1: Select 4 datasets](#11-select-4-datasets)
  - [1.2: Dataset exploration](#12-dataset-exploration)
  - [1.3: Dataset selection](#13-dataset-selection)
  - [1.4: End goal](#14-end-goal)
- [Important note](#important-note)
- [Task 2: Exploring your dataset](#task-2-exploring-your-dataset)
  - [2.1: Further exploration of the
    data](#21-further-exploration-of-the-data)
    - [2.1.3: Missing data per variable](#213-missing-data-per-variable)
    - [2.1.1: Plot the distribution of a numeric
      variable](#211-plot-the-distribution-of-a-numeric-variable)
    - [2.1.8: Use a density plot to explore any of your
      variables](#218-use-a-density-plot-to-explore-any-of-your-variables)
    - [2.1.4: Explore the relationship between variables in a
      plot](#214-explore-the-relationship-between-variables-in-a-plot)
  - [2.2: Explanation](#22-explanation)
    - [2.2.3: Explanation of missing data
      exploration](#223-explanation-of-missing-data-exploration)
    - [2.2.1: Explanation of distribution plot
      exploration](#221-explanation-of-distribution-plot-exploration)
    - [2.2.8: Explanation of density plot
      exploration](#228-explanation-of-density-plot-exploration)
    - [2.2.4: Explanation of relationships between variables
      exploration](#224-explanation-of-relationships-between-variables-exploration)
- [Task 3: Choose research questions](#task-3-choose-research-questions)
- [Overall reproducibility/Cleanliness/Coherence
  Checklist](#overall-reproducibilitycleanlinesscoherence-checklist)
  - [Coherence (0.5 points)](#coherence-05-points)
  - [Error-free code (3 points)](#error-free-code-3-points)
  - [Main README (1 point)](#main-readme-1-point)
  - [Output (1 point)](#output-1-point)
  - [Tagged release (0.5 points)](#tagged-release-05-points)
    - [Attribution](#attribution)

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

## 1.1: Select 4 datasets

1.1 Instructions: **(1 point)** Out of the 7 datasets available in the
`datateachr` package, choose **4** that appeal to you based on their
description. Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

**Answer:**

<!-------------------------- Start your work below ---------------------------->

1: `steam_games`: This dataset contains information about video games
available on Steam, an online compute website.

2: `vancouver_trees`: This dataset contains information about public
trees in Vancouver.

3: `flow_sample`: This dataset contains information about the annual
flow rate extremes of the Bow River, near Banff in Alberta.

4: `cancer_sample`: This dataset contains information about breast
cancer patients at the University of Wisconsin Hospital.

<!----------------------------------------------------------------------------->

## 1.2: Dataset exploration

1.2 Instructions: **(6 points)** One way to narrowing down your
selection is to *explore* the datasets. Use your knowledge of dplyr to
find out at least *3* attributes about each of these datasets (an
attribute is something such as number of rows, variables, class type…).
The goal here is to have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

**Answer:**

<!-------------------------- Start your work below ---------------------------->

Use of glimpse(), as it returns a digestible summary of information
concerning a dataset, such as the name, number (columns), and type of
the variables, and the number of observations (rows). Moreover, I used
the help operator to read descriptions of the variables in each dataset.

``` r
glimpse(steam_games)
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

``` r
help(steam_games)
```

    ## démarrage du serveur d'aide httpd ... fini

``` r
glimpse(vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

``` r
help(vancouver_trees)
```

``` r
glimpse(flow_sample)
```

    ## Rows: 218
    ## Columns: 7
    ## $ station_id   <chr> "05BB001", "05BB001", "05BB001", "05BB001", "05BB001", "0…
    ## $ year         <dbl> 1909, 1910, 1911, 1912, 1913, 1914, 1915, 1916, 1917, 191…
    ## $ extreme_type <chr> "maximum", "maximum", "maximum", "maximum", "maximum", "m…
    ## $ month        <dbl> 7, 6, 6, 8, 6, 6, 6, 6, 6, 6, 6, 7, 6, 6, 6, 7, 5, 7, 6, …
    ## $ day          <dbl> 7, 12, 14, 25, 11, 18, 27, 20, 17, 15, 22, 3, 9, 5, 14, 5…
    ## $ flow         <dbl> 314, 230, 264, 174, 232, 214, 236, 309, 174, 345, 185, 24…
    ## $ sym          <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…

``` r
help(flow_sample)
```

``` r
glimpse(cancer_sample)
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…

``` r
help(cancer_sample)
```

<!----------------------------------------------------------------------------->

## 1.3: Dataset selection

1.3 Instructions: **(1 point)** Now that you’ve explored the 4 datasets
that you were initially most interested in, let’s narrow it down to 1.
What lead you to choose this one? Briefly explain your choice below.

**Answer:**

<!-------------------------- Start your work below ---------------------------->

An ideal dataset would have a large amount of useful data, with both
continuous and categorical variables, and numerous observations per
variable.

1.  In the `steam_games` dataset, while there are numerous
    variables (21) and observations (40,833), the number of continuous
    variables is limited.

2.  The `vancouver_trees` dataset has a large number of variables (20)
    and observations (146,611). It has both categorical and continuous
    variables.

3.  In the `flow_sample` dataset, the number of variables (7) and
    observations (218) is comparatively lower than other datasets. The
    number of categorical variables is also limited.

4.  The `cancer_sample` dataset has a large number of variables (32) and
    a reasonable number of observations (569). However, the number of
    categorical variables is limited.

Due to these observations, `vancouver_trees` was selected as the dataset
of choice. It has a high number of variables and the highest number of
observations of the four datasets I was most interested in initially.
Moreover, it has a balanced mix of categorical and continuous variables,
which will allow for interesting analyses.

<!----------------------------------------------------------------------------->

## 1.4: End goal

1.4 Instructions: **(2 points)** Time for a final decision! Going back
to the beginning, it’s important to have an *end goal* in mind. For
example, if I had chosen the `titanic` dataset for my project, I might
have wanted to explore the relationship between survival and other
variables. Try to think of 1 research question that you would want to
answer with your dataset. Note it down below.

**Answer:**

<!-------------------------- Start your work below ---------------------------->

I believe investigating the relationship between tree localisation in
Vancouver and other variables, such as species, age, number, and
dimensions would prove very interesting.

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

## 2.1: Further exploration of the data

2.1 Instructions: **(12 points)** Complete *4 out of the following 8
exercises* to dive deeper into your data. All datasets are different and
therefore, not all of these tasks may make sense for your data - which
is why you should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

**The four selected exercises have been bolded in the list below:**

1.  **Plot the distribution of a numeric variable.**

2.  Create a new variable based on other variables in your data (only if
    it makes sense)

3.  **Investigate how many missing values there are per variable. Can
    you find a way to plot this?**

4.  **Explore the relationship between 2 variables in a plot.**

5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…

6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!

7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.

8.  **Use a density plot to explore any of your variables (that are
    suitable for this type of plot).**

<!-------------------------- Start your work below ---------------------------->

### 2.1.3: Missing data per variable

Before using and exploring any data, it is good practice to clean it
first.

``` r
dim(vancouver_trees[duplicated(vancouver_trees$tree_id),])[1]
```

    ## [1] 0

The above code shows there are no duplicates in the `vancouver_trees`
dataset.

``` r
sum(is.null(vancouver_trees))
```

    ## [1] 0

The above code shows there are no nulls, thus all variables received a
value.

``` r
sum(is.na(vancouver_trees))
```

    ## [1] 191135

The code above shows there are 191,135 observations that received a NA
value. We can look at all of these:

``` r
vancouver_trees_list_NA <- vancouver_trees[rowSums(is.na(vancouver_trees)) > 0, ]
vancouver_trees_list_NA
```

    ## # A tibble: 104,752 × 20
    ##    tree_id civic_number std_street genus_name species_name cultivar_name
    ##      <dbl>        <dbl> <chr>      <chr>      <chr>        <chr>        
    ##  1  149563          450 W 58TH AV  ZELKOVA    SERRATA      <NA>         
    ##  2  149579         4994 WINDSOR ST STYRAX     JAPONICA     <NA>         
    ##  3  149604         5032 WINDSOR ST ACER       CAMPESTRE    <NA>         
    ##  4  149616          585 W 61ST AV  PYRUS      CALLERYANA   CHANTICLEER  
    ##  5  149626          736 E 39TH AV  TILIA      EUCHLORA   X <NA>         
    ##  6  149636          812 E 39TH AV  TILIA      EUCHLORA   X <NA>         
    ##  7  149646          505 E 16TH AV  HIBISCUS   SYRIACA      <NA>         
    ##  8  149647          509 E 16TH AV  STYRAX     JAPONICA     <NA>         
    ##  9  149658         5208 WINDSOR ST STYRAX     JAPONICA     <NA>         
    ## 10  149680         5311 WINDSOR ST ACER       CAMPESTRE    <NA>         
    ## # ℹ 104,742 more rows
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <dbl>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <dbl>,
    ## #   diameter <dbl>, curb <chr>, date_planted <date>, longitude <dbl>,
    ## #   latitude <dbl>

This visualization method is however not very digestible. To improve the
legibility, the information needs to be collected and summarized with
the following code:

``` r
vancouver_trees_allNA <- vancouver_trees%>% summarise(across(everything(), ~ sum(is.na(.))))
vancouver_trees_allNA <- as.data.frame(t(as.matrix(vancouver_trees_allNA))) 
vancouver_trees_allNA$variable <- rownames(vancouver_trees_allNA)
rownames(vancouver_trees_allNA) <- 1:nrow(vancouver_trees_allNA)
colnames(vancouver_trees_allNA) <- c("na_count", "Variable")
vancouver_trees_allNA
```

    ##    na_count           Variable
    ## 1         0            tree_id
    ## 2         0       civic_number
    ## 3         0         std_street
    ## 4         0         genus_name
    ## 5         0       species_name
    ## 6     67559      cultivar_name
    ## 7         0        common_name
    ## 8         0           assigned
    ## 9         0       root_barrier
    ## 10     1486         plant_area
    ## 11        0    on_street_block
    ## 12        0          on_street
    ## 13        0 neighbourhood_name
    ## 14        0   street_side_name
    ## 15        0    height_range_id
    ## 16        0           diameter
    ## 17        0               curb
    ## 18    76548       date_planted
    ## 19    22771          longitude
    ## 20    22771           latitude

Finally, this let us plot the number of NA values per variable.

``` r
ggplot(vancouver_trees_allNA, aes(y=Variable))+
  geom_bar(aes(weight=na_count))+
  theme_bw() +
  xlab("Number of NA values")
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

### 2.1.1: Plot the distribution of a numeric variable

To start the more in depth exploration of this dataset, the temporal
distribution of tree plantation was investigated:

``` r
# Removal of all NA date_planted rows.
vancouver_trees_noNA_date <- vancouver_trees %>% drop_na(date_planted)
ggplot(vancouver_trees_noNA_date, aes(date_planted)) + 
  geom_bar()+
  ylim(0,450) + # max number planted on a day (2003-11-14) is 410 
  theme_bw() +
  ylab("Number of trees planted") +
  xlab("Date of plantation")
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

This function plots the data for every single day, however, and as such,
it’s legibility is poor. It is more interesting to visualize the number
of trees planted by year, given by this code:

``` r
vancouver_trees_year <- vancouver_trees_noNA_date %>%
  mutate(year=lubridate::year(date_planted)) 

ggplot(vancouver_trees_year, aes(year))+
  geom_bar()+
  theme_bw() +
  ylab("Number of trees planted") +
  xlab("Date of plantation")
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-13-1.png)<!-- -->

### 2.1.8: Use a density plot to explore any of your variables

Next, the spatial distribution of the trees was investigated:

``` r
# Removal of all NA latitude and longitude rows.
vancouver_trees_noNA_coordinates <- vancouver_trees %>% drop_na(latitude, longitude)

#install.packages("hexbin")
ggplot(vancouver_trees_noNA_coordinates, aes(latitude, longitude)) +
  geom_hex(bins=70) +
  scale_fill_continuous(type = "viridis") +
  theme_bw()
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-14-1.png)<!-- -->

While this plot offers an intuitive representation of the spatial
density of trees in Vancouver, it may not be the most accurate spatial
representation due to the high amount of NA values. This is given by:

``` r
sum(is.na(vancouver_trees$longitude))
```

    ## [1] 22771

``` r
sum(is.na(vancouver_trees$latitude))
```

    ## [1] 22771

However, not all variables that contain spatial information have missing
values:

``` r
sum(is.na(vancouver_trees$neighbourhood_name))
```

    ## [1] 0

One way to obtain a more accurate, if less intuitive, representation of
the spatial distribution of trees in Vancouver would be to investigate
their distribution in neighborhoods instead, as there is no missing
values for this variable.

``` r
ggplot(vancouver_trees, aes(y=neighbourhood_name)) + 
  geom_bar() +
  theme_bw() +
  ylab("Neighbourhood name") +
  xlab("Number of trees")
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->

These two plots both provide information on the spatial position of the
trees in a complimentary way.

### 2.1.4: Explore the relationship between variables in a plot

Finally, the relationship between a number of variables was
investigated. However, to calculate correlations numerical values are
needed. Categorical data were thus encoded to allow calculations. This
was done using the code found
[here](https://www.r-bloggers.com/2020/02/a-guide-to-encoding-categorical-features-using-r/).

``` r
# Encoding function
encode <- function(x, order = unique(x)) {
  x <- as.numeric(factor(x, levels = order, exclude = NULL))}

#Encode the categorical data of interest
encoded_vancouver_trees <- vancouver_trees_year
encoded_vancouver_trees$common_name <- encode(encoded_vancouver_trees$common_name)
encoded_vancouver_trees$assigned <- encode(encoded_vancouver_trees$assigned)
encoded_vancouver_trees$root_barrier <- encode(encoded_vancouver_trees$root_barrier)
encoded_vancouver_trees$plant_area <- encode(encoded_vancouver_trees$plant_area)
encoded_vancouver_trees$neighbourhood_name <- encode(encoded_vancouver_trees$neighbourhood_name)
encoded_vancouver_trees$plant_area <- encode(encoded_vancouver_trees$plant_area)
encoded_vancouver_trees$curb <- encode(encoded_vancouver_trees$curb)
```

The encoded data was then used to create a heatmap. Some redundant
variables were excluded (e.g. `common_name` is used instead of
`genus_name` and `species_name`).

``` r
#Select the variables to use in the heatmap
vancouver_trees_heatmap <- encoded_vancouver_trees %>% select(common_name, assigned, root_barrier, plant_area, neighbourhood_name, height_range_id, diameter, curb, year, longitude, latitude)
vancouver_trees_heatmap
```

    ## # A tibble: 70,063 × 11
    ##    common_name assigned root_barrier plant_area neighbourhood_name
    ##          <dbl>    <dbl>        <dbl>      <dbl>              <dbl>
    ##  1           1        1            1          1                  1
    ##  2           2        1            1          1                  1
    ##  3           3        1            1          2                  2
    ##  4           4        2            1          2                  2
    ##  5           5        1            1          2                  2
    ##  6           6        1            1          3                  2
    ##  7           6        1            1          3                  2
    ##  8           6        1            1          4                  2
    ##  9           4        1            1          4                  2
    ## 10           7        1            1          5                  2
    ## # ℹ 70,053 more rows
    ## # ℹ 6 more variables: height_range_id <dbl>, diameter <dbl>, curb <dbl>,
    ## #   year <dbl>, longitude <dbl>, latitude <dbl>

``` r
#Calculate the correlations
correlation <- round(cor(vancouver_trees_heatmap, use= "complete.obs"), 2) 
  # ignores NA values when computing correlation
correlation
```

    ##                    common_name assigned root_barrier plant_area
    ## common_name               1.00     0.03         0.01       0.04
    ## assigned                  0.03     1.00         0.01      -0.03
    ## root_barrier              0.01     0.01         1.00      -0.02
    ## plant_area                0.04    -0.03        -0.02       1.00
    ## neighbourhood_name        0.02     0.04        -0.03       0.11
    ## height_range_id          -0.02    -0.04        -0.20      -0.01
    ## diameter                 -0.02    -0.06        -0.12      -0.03
    ## curb                     -0.03     0.02         0.00       0.03
    ## year                      0.11     0.03         0.20       0.05
    ## longitude                 0.00     0.04         0.08      -0.13
    ## latitude                  0.03     0.00         0.03       0.12
    ##                    neighbourhood_name height_range_id diameter  curb  year
    ## common_name                      0.02           -0.02    -0.02 -0.03  0.11
    ## assigned                         0.04           -0.04    -0.06  0.02  0.03
    ## root_barrier                    -0.03           -0.20    -0.12  0.00  0.20
    ## plant_area                       0.11           -0.01    -0.03  0.03  0.05
    ## neighbourhood_name               1.00            0.00    -0.02 -0.02  0.03
    ## height_range_id                  0.00            1.00     0.58  0.10 -0.60
    ## diameter                        -0.02            0.58     1.00  0.05 -0.45
    ## curb                            -0.02            0.10     0.05  1.00 -0.15
    ## year                             0.03           -0.60    -0.45 -0.15  1.00
    ## longitude                       -0.20            0.02     0.04  0.07 -0.07
    ## latitude                         0.22            0.07     0.06  0.00 -0.03
    ##                    longitude latitude
    ## common_name             0.00     0.03
    ## assigned                0.04     0.00
    ## root_barrier            0.08     0.03
    ## plant_area             -0.13     0.12
    ## neighbourhood_name     -0.20     0.22
    ## height_range_id         0.02     0.07
    ## diameter                0.04     0.06
    ## curb                    0.07     0.00
    ## year                   -0.07    -0.03
    ## longitude               1.00     0.04
    ## latitude                0.04     1.00

``` r
#Adapt the correlations for use in the heatmap
#install.packages("reshape2")
melted_correlation <- reshape2::melt(correlation)
head(melted_correlation)
```

    ##                 Var1        Var2 value
    ## 1        common_name common_name  1.00
    ## 2           assigned common_name  0.03
    ## 3       root_barrier common_name  0.01
    ## 4         plant_area common_name  0.04
    ## 5 neighbourhood_name common_name  0.02
    ## 6    height_range_id common_name -0.02

``` r
#Create the heatmap
ggplot(melted_correlation, aes(x=Var1, y=Var2, fill=value)) + 
  geom_tile() +
  theme(axis.text.x = element_text(angle=90, vjust = 0.5, hjust = 1))+
  scale_fill_gradient2(low = "blue", high = "red", mid = "white", 
   midpoint = 0, limit = c(-1,1), name="Pearson\nCorrelation") 
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-22-1.png)<!-- -->

## 2.2: Explanation

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

### 2.2.3: Explanation of missing data exploration

Before exploring a new dataset, it is always useful to know the state of
it and of its variables. This helps us minimize background noise, and
helps us make a more informed decision on the potential for
generalization of our data. Moreover, it can give us information that
may have not been found in further explorations, and hint at other
possibilities.

For example, we found here that 76,548 observations were missing in the
`date_planted` variables. Not only would this information have not been
known without investigating the missing data, but this also hints that
maybe tree plantation did not start in 1989 but before, and only the
recording of plantation started at that date.

In the following explorations, all missing observations will not be
included in the plots.

### 2.2.1: Explanation of distribution plot exploration

Distributions permit efficient summary and visualization of data. From
these, we can quickly determine a number of information, such as
potential peaks, the normal range, etc.

Here, we looked at the number of trees planted dependent on the date and
year. This distribution helps us determine the evolution of the
plantation effort in Vancouver.

The first plot informs us that there are periods throughout the year
during which the planting takes place. The second plot, done by years,
informs us that record keeping began in 1989, and after a few years
reached a nearly two decades long plateau at around 3000 planted trees
per year, before decreasing in recent times.

This could lead to further analysis, such as the spatial evolution of
plantation targets. Are there privileged sites, now or before?

### 2.2.8: Explanation of density plot exploration

Density plots show us the distribution of variables. Here we looked at
the `latitude` and `longitude` of planted trees. Whereas a distribution
would have given us a map of the location of all planted trees, this
density plot does the same while also informing us of the degree to
which each area is wooded. We can thus quickly determine the exact
localisations that are the most or least wooded. This is a great spatial
representation of the trees in Vancouver.

Here, a bins of 70 was selected, as it allowed the best spatial accuracy
while maintaining the ability to display a density gradient that would
disappear with a too fine map (and thus a too high bins).

### 2.2.4: Explanation of relationships between variables exploration

Exploring the relationship between multiple variables allows us to see
how different factors may influence others. It is important to realize
that some variables may not be independent.

This heatmap, which shows the correlations between numerous variables,
gives us a lot of points to further investigate.

For example, it shows us that there is a strong positive relationship
between the diameter of a tree and its height, and both the diameter and
height of a tree is negatively correlated to its age. While this is
rather expected, this heatmap shows other unknown links. For example,
there seems to be a link between the year, and which trees were most
planted and whether a root barrier was installed.

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

**Answer:**

Here are four different research questions that would be interesting to
explore:

1.  How has the quantity of trees planted each year changed in specific
    areas?

2.  Do localisations differ in the variety of types of trees planted
    there?

3.  Has the planting technique (presence of a root barrier and tree
    grate) evolved?

4.  Have different types of trees been favored through time?

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
