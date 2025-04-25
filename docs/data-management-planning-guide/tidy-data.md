# Tidy Data: Principles and Practice

## Introduction

Tidy data is a standardized approach to organizing datasets where:

1.  Each variable forms a column
2.  Each observation forms a row
3.  Each value occupies a single cell

These principles create a consistent and logical structure that
simplifies data analysis, visualization, and manipulation. When data is
tidy, it works seamlessly with data analysis tools and facilitates more
efficient analysis workflows.

In the following sections, we’ll explore common untidy data scenarios
and demonstrate techniques to transform them into tidy formats. While
not exhaustive, these examples illustrate the fundamental principles of
tidy data transformation.

<!-- prettier-ignore -->
!!! note 
    The examples presented here use truncated datasets for clarity and readability.

## Common Untidy Data Scenarios

### Scenario 1: Column Headers Are Values, Not Variable Names

This dataset from the Pew Research Center contains the number of people
in each income group for various religions:

| religion                | \<\$10k | \$10-20k | \$20-30k | \$30-40k | \$40-50k | \$50-75k |
| :---------------------- | ------: | -------: | -------: | -------: | -------: | -------: |
| Agnostic                |      27 |       34 |       60 |       81 |       76 |      137 |
| Atheist                 |      12 |       27 |       37 |       52 |       35 |       70 |
| Buddhist                |      27 |       21 |       30 |       34 |       33 |       58 |
| Catholic                |     418 |      617 |      732 |      670 |      638 |     1116 |
| Don’t know/refused      |      15 |       14 |       15 |       11 |       10 |       35 |
| Evangelical Prot        |     575 |      869 |     1064 |      982 |      881 |     1486 |
| Hindu                   |       1 |        9 |        7 |        9 |       11 |       34 |
| Historically Black Prot |     228 |      244 |      236 |      238 |      197 |      223 |
| Jehovah’s Witness       |      20 |       27 |       24 |       24 |       21 |       30 |
| Jewish                  |      19 |       19 |       25 |       25 |       30 |       95 |
| Mainline Prot           |     289 |      495 |      619 |      655 |      651 |     1107 |
| Mormon                  |      29 |       40 |       48 |       51 |       56 |      112 |
| Muslim                  |       6 |        7 |        9 |       10 |        9 |       23 |
| Orthodox                |      13 |       17 |       23 |       32 |       32 |       47 |
| Other Christian         |       9 |        7 |       11 |       13 |       13 |       14 |
| Other Faiths            |      20 |       33 |       40 |       46 |       49 |       63 |
| Other World Religions   |       5 |        2 |        3 |        4 |        2 |        7 |
| Unaffiliated            |     217 |      299 |      374 |      365 |      341 |      528 |

**Problem:** The column names represent _values_ of an income variable
rather than distinct variables themselves.

**Solution:** We need to pivot the data to create two new columns:

- `income`: Contains the income groups (previously column names)
- `frequency`: Contains the count of people (previously cell values)

| religion | income   | frequency |
| :------- | :------- | --------: |
| Agnostic | \<\$10k  |        27 |
| Agnostic | \$10-20k |        34 |
| Agnostic | \$20-30k |        60 |
| Agnostic | \$30-40k |        81 |
| Agnostic | \$40-50k |        76 |
| Agnostic | \$50-75k |       137 |
| Atheist  | \<\$10k  |        12 |
| Atheist  | \$10-20k |        27 |
| Atheist  | \$20-30k |        37 |
| Atheist  | \$30-40k |        52 |
| Atheist  | \$40-50k |        35 |
| Atheist  | \$50-75k |        70 |

After transformation, the dataset is tidy because each column represents
a variable and each row represents an observation.

### Scenario 2: Multiple Variables in a Single Column

The `who`
[dataset](https://www.who.int/teams/global-tuberculosis-programme/data)
contains information about tuberculosis cases across different
countries:

| country               | year | new_sp_m014 | new_sp_m1524 | new_sp_m2534 | new_sp_m3544 |
| :-------------------- | ---: | ----------: | -----------: | -----------: | -----------: |
| Sao Tome and Principe | 2006 |           0 |            5 |            8 |            4 |
| Serbia & Montenegro   | 1995 |          10 |          108 |          204 |          317 |
| Paraguay              | 2006 |          20 |          188 |          221 |          143 |
| Canada                | 2006 |           2 |           34 |           34 |           33 |
| Bahamas               | 2011 |           0 |            2 |            3 |            6 |
| United Arab Emirates  | 2012 |           0 |            2 |            4 |            4 |

**Problems:**

1.  Column names contain values, not variable names (similar to Scenario
    1.
2.  Multiple variables are encoded in a single column name

**Step 1:** First, we pivot the dataset to address the column name
issue:

| country               | year | demographic  | cases |
| :-------------------- | ---: | :----------- | ----: |
| Sao Tome and Principe | 2006 | new_sp_m014  |     0 |
| Sao Tome and Principe | 2006 | new_sp_m1524 |     5 |
| Sao Tome and Principe | 2006 | new_sp_m2534 |     8 |
| Sao Tome and Principe | 2006 | new_sp_m3544 |     4 |
| Serbia & Montenegro   | 1995 | new_sp_m014  |    10 |
| Serbia & Montenegro   | 1995 | new_sp_m1524 |   108 |

**Step 2:** Next, we separate the `demographic` column into its
component variables:

- `method`: Diagnosis method (e.g., `new_sp` = new smear positive)
- `sex`: Patient sex (m = male, f = female)
- `age_group`: Patient age range

Let’s analyze `new_sp_m014` from the first row:

- `new_sp`: Method of diagnosis (other possibilities include `rel` =
  relapse, `sn` = negative pulmonary smear)
- `m`: Sex (male)
- `014`: Age group (0-14 years)

| country               | year | method | sex | age_group | cases |
| :-------------------- | ---: | :----- | :-- | :-------- | ----: |
| Sao Tome and Principe | 2006 | new_sp | m   | 0-14      |     0 |
| Sao Tome and Principe | 2006 | new_sp | m   | 15-24     |     5 |
| Sao Tome and Principe | 2006 | new_sp | m   | 25-34     |     8 |
| Sao Tome and Principe | 2006 | new_sp | m   | 35-44     |     4 |
| Serbia & Montenegro   | 1995 | new_sp | m   | 0-14      |    10 |
| Serbia & Montenegro   | 1995 | new_sp | m   | 15-24     |   108 |

With the data now tidy, we can easily analyze case counts by method,
sex, and age group:

| method | sex | age_group |   n |
| :----- | :-- | :-------- | --: |
| new_sp | m   | 0-14      |  10 |
| new_sp | m   | 15-24     | 113 |
| new_sp | m   | 25-34     |   8 |
| new_sp | m   | 35-44     |   4 |

### Scenario 3: Variables Stored in Both Rows and Columns

The `temperature` dataset contains daily weather data from a Mexican
weather station:

| id      | year | month | element |  d1 |   d2 |   d3 |  d4 |   d5 |  d6 |  d7 |  d8 | d9  |  d10 |  d11 | d12 | d13 | d14 | d15 |  d16 | d17 | d18 | d19 | d20 | d21 | d22 |  d23 | d24 | d25 | d26 |  d27 | d28 | d29 |  d30 | d31 |
| :------ | ---: | ----: | :------ | --: | ---: | ---: | --: | ---: | --: | --: | --: | :-- | ---: | ---: | :-- | --: | --: | --: | ---: | --: | :-- | :-- | :-- | :-- | :-- | ---: | :-- | --: | --: | ---: | --: | --: | ---: | --: |
| MX17004 | 2010 |     1 | tmax    |  NA |   NA |   NA |  NA |   NA |  NA |  NA |  NA | NA  |   NA |   NA | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA |   NA |  NA |  NA | 27.8 |  NA |
| MX17004 | 2010 |     1 | tmin    |  NA |   NA |   NA |  NA |   NA |  NA |  NA |  NA | NA  |   NA |   NA | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA |   NA |  NA |  NA | 14.5 |  NA |
| MX17004 | 2010 |     2 | tmax    |  NA | 27.3 | 24.1 |  NA |   NA |  NA |  NA |  NA | NA  |   NA | 29.7 | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  | 29.9 | NA  |  NA |  NA |   NA |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     2 | tmin    |  NA | 14.4 | 14.4 |  NA |   NA |  NA |  NA |  NA | NA  |   NA | 13.4 | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  | 10.7 | NA  |  NA |  NA |   NA |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     3 | tmax    |  NA |   NA |   NA |  NA | 32.1 |  NA |  NA |  NA | NA  | 34.5 |   NA | NA  |  NA |  NA |  NA | 31.1 |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA |   NA |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     3 | tmin    |  NA |   NA |   NA |  NA | 14.2 |  NA |  NA |  NA | NA  | 16.8 |   NA | NA  |  NA |  NA |  NA | 17.6 |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA |   NA |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     4 | tmax    |  NA |   NA |   NA |  NA |   NA |  NA |  NA |  NA | NA  |   NA |   NA | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA | 36.3 |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     4 | tmin    |  NA |   NA |   NA |  NA |   NA |  NA |  NA |  NA | NA  |   NA |   NA | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA | 16.7 |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     5 | tmax    |  NA |   NA |   NA |  NA |   NA |  NA |  NA |  NA | NA  |   NA |   NA | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA | 33.2 |  NA |  NA |   NA |  NA |
| MX17004 | 2010 |     5 | tmin    |  NA |   NA |   NA |  NA |   NA |  NA |  NA |  NA | NA  |   NA |   NA | NA  |  NA |  NA |  NA |   NA |  NA | NA  | NA  | NA  | NA  | NA  |   NA | NA  |  NA |  NA | 18.2 |  NA |  NA |   NA |  NA |

**Problems:**

1.  Daily measurements are spread across columns (`d1` through `d31`)
2.  The `element` column contains two different variables (`tmin` and
    `tmax`)

**Step 1:** First, we pivot the daily measurements into rows:

| id      | year | month | element | day | value |
| :------ | ---: | ----: | :------ | :-- | ----: |
| MX17004 | 2010 |     1 | tmax    | d30 |  27.8 |
| MX17004 | 2010 |     1 | tmin    | d30 |  14.5 |
| MX17004 | 2010 |     2 | tmax    | d2  |  27.3 |
| MX17004 | 2010 |     2 | tmax    | d3  |  24.1 |
| MX17004 | 2010 |     2 | tmax    | d11 |  29.7 |
| MX17004 | 2010 |     2 | tmax    | d23 |  29.9 |

**Step 2:** Next, we pivot the `element` types into separate columns:

| id      | year | month | day | tmax | tmin |
| :------ | ---: | ----: | :-- | ---: | ---: |
| MX17004 | 2010 |     1 | d30 | 27.8 | 14.5 |
| MX17004 | 2010 |     2 | d2  | 27.3 |   NA |
| MX17004 | 2010 |     2 | d3  | 24.1 |   NA |
| MX17004 | 2010 |     2 | d11 | 29.7 |   NA |
| MX17004 | 2010 |     2 | d23 | 29.9 |   NA |

The final dataset is now tidy, with each variable in its own column and
each observation in a single row.

## Conclusion

While tidying data may initially require more effort, the resulting
structure provides significant benefits throughout the analysis
pipeline. By following the principles of tidy data, analysts can create
more maintainable, efficient, and reproducible workflows.

For further exploration of tidy data concepts, see [Tidy
Data](https://vita.had.co.nz/papers/tidy-data.pdf) by Hadley Wickham.
Most examples in this document come from the [tidyr vignette on tidy
data](https://tidyr.tidyverse.org/articles/tidy-data.html).
