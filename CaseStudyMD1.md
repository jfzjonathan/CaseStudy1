Source Documents
----------------

``` r
## Saved the csv documents on GitHub, the code below process information from GitHub instead of our local computers.

require(RCurl)
```

    ## Loading required package: RCurl

    ## Warning: package 'RCurl' was built under R version 3.4.3

    ## Loading required package: bitops

    ## Warning: package 'bitops' was built under R version 3.4.1

``` r
## Reading from beers csv. The csv is saved on GitHub

Beers <- data.frame(read.csv(text = getURL("https://raw.githubusercontent.com/jfzjonathan/casestudy1/master/Beers.csv"),header = TRUE,sep=","))

## Reading from breweries csv. The csv is saved on GitHub

Breweries <- data.frame(read.csv(text = getURL("https://raw.githubusercontent.com/jfzjonathan/casestudy1/master/Breweries.csv"),header = TRUE,sep=","))
```

Making the raw data tidy data
-----------------------------

``` r
## Renaming Beer columns

colnames(Beers) <- c("Beer Name", "Beer_ID", "ABV", "IBU", "Brewery_ID","Beet Style", "Ounces")


## Renaming Breweries columns

colnames(Breweries) <- c("Brew_ID", "Brewery Name", "Brewery City", "Brewery State")
```

``` r
## Displaying the first rows of Beer to make sure they transfer properly


library(knitr)
knitr::kable(head(Beers))
```

| Beer Name           |  Beer\_ID|    ABV|  IBU|  Brewery\_ID| Beet Style                     |  Ounces|
|:--------------------|---------:|------:|----:|------------:|:-------------------------------|-------:|
| Pub Beer            |      1436|  0.050|   NA|          409| American Pale Lager            |      12|
| Devil's Cup         |      2265|  0.066|   NA|          178| American Pale Ale (APA)        |      12|
| Rise of the Phoenix |      2264|  0.071|   NA|          178| American IPA                   |      12|
| Sinister            |      2263|  0.090|   NA|          178| American Double / Imperial IPA |      12|
| Sex and Candy       |      2262|  0.075|   NA|          178| American IPA                   |      12|
| Black Exodus        |      2261|  0.077|   NA|          178| Oatmeal Stout                  |      12|

``` r
## Displaying the first rows of Breweries to make sure they transfer properly


knitr::kable(head(Breweries))
```

|  Brew\_ID| Brewery Name              | Brewery City  | Brewery State |
|---------:|:--------------------------|:--------------|:--------------|
|         1| NorthGate Brewing         | Minneapolis   | MN            |
|         2| Against the Grain Brewery | Louisville    | KY            |
|         3| Jack's Abby Craft Lagers  | Framingham    | MA            |
|         4| Mike Hess Brewing Company | San Diego     | CA            |
|         5| Fort Point Beer Company   | San Francisco | CA            |
|         6| COAST Brewing Company     | Charleston    | SC            |

1. How many breweries are present in each state?
------------------------------------------------

2. Merge beer data with the breweries data. Print the first 6 observations and the last six observations to check the merged file.
----------------------------------------------------------------------------------------------------------------------------------

3. Report the number of NA's in each column.
--------------------------------------------

4. Compute the median alcohol content and international bitterness unit for each state. Plot a bar chart to compare.
--------------------------------------------------------------------------------------------------------------------

5. Which state has the maximum alcoholic (ABV) beer? Which state has the most bitter (IBU) beer?
------------------------------------------------------------------------------------------------

6. Summary statistics for the ABV variable.
-------------------------------------------

7. Is there an apparent relationship between the bitterness of the beer and its alcoholic content? Draw a scatter plot.
-----------------------------------------------------------------------------------------------------------------------
