NHL Data
================
Todd Idol
9/8/2020

R Markdown
----------

This is an R Markdown document. Markdown is a simple formatting syntax
for authoring HTML, PDF, and MS Word documents. For more details on
using R Markdown see
<a href="http://rmarkdown.rstudio.com" class="uri">http://rmarkdown.rstudio.com</a>.

When you click the **Knit** button a document will be generated that
includes both content as well as the output of any embedded R code
chunks within the document. You can embed an R code chunk like this:

    summary(cars)

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

Including Plots
---------------

You can also embed plots, for example:

![](README_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.

    crabs <- tbl_df(readr::read_delim("C:/Users/idolt/Desktop/ST558/Module 7/crabs.txt", delim = "   "))
    knitr::kable(head(crabs))

| color | spine | width | satell | weight |   y | X7  |
|------:|:------|:------|:-------|:-------|----:|:----|
|     3 | 3     | 28.3  | 8      | 3050   |   1 | NA  |
|     4 | 3     | 22.5  | 0      | 1550   |   0 | NA  |
|     2 | 1     | 26.0  | 9      | 2300   |   1 | NA  |
|     4 | 3     | 24.8  | 0      | 2100   |   0 | NA  |
|     4 | 3     | 26.0  | 4      | 2600   |   1 | NA  |
|     3 | 3     | 23.8  | 0      | 2100   |   0 | NA  |

Test for Credentials
====================

Working
=======

    knitr::kable(head(iris))

| Sepal.Length | Sepal.Width | Petal.Length | Petal.Width | Species |
|-------------:|------------:|-------------:|------------:|:--------|
|          5.1 |         3.5 |          1.4 |         0.2 | setosa  |
|          4.9 |         3.0 |          1.4 |         0.2 | setosa  |
|          4.7 |         3.2 |          1.3 |         0.2 | setosa  |
|          4.6 |         3.1 |          1.5 |         0.2 | setosa  |
|          5.0 |         3.6 |          1.4 |         0.2 | setosa  |
|          5.4 |         3.9 |          1.7 |         0.4 | setosa  |
