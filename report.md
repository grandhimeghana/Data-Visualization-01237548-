HW 1, CS 625, Spring 2023
================
Meghana Grandhi
Jan 19, 2023

## Git, GitHub

1.  *What is your GitHub username?*

    grandhimeghana

2.  *What is the URL of your remote GitHub repo (created through
    Mr. Kennedy’s exercises)?*

    <https://github.com/grandhimeghana/Data-Visualization-01237548->

## R

The command below will load the tidyverse package. If you have installed
R, RStudio, and the tidyverse package, it should display a list of
loaded packages and their versions.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.4.0      ✔ purrr   1.0.1 
    ## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
    ## ✔ tidyr   1.2.1      ✔ stringr 1.5.0 
    ## ✔ readr   2.1.3      ✔ forcats 0.5.2 
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

## R Markdown

1.  *Create a bulleted list with at least 3 items*

- Apple
- Orange
- Banana

2.  *Write a single paragraph that demonstrates the use of italics,
    bold, bold italics, code, and includes a link. The paragraph does
    not have to make sense.*

    Hi My Name is *Meghana Grandhi*

    Hi My Name is **Meghana Grandhi**

    Hi My Name is ***Meghana Grandhi***

    Hi My Name is `Meghana Grandhi`

My favorite search engine is [Duck Duck Go](https://duckduckgo.com).

3.  *Create a level 3 heading*

### Heading Level 3

## R

#### Data Visualization Exercises

1.  (Q2) *How many rows are in mpg? How many columns?*

    There are 234 rows and 11 Columns

    ``` r
    ggplot2::mpg
    ```

        ## # A tibble: 234 × 11
        ##    manufacturer model      displ  year   cyl trans drv     cty   hwy fl    class
        ##    <chr>        <chr>      <dbl> <int> <int> <chr> <chr> <int> <int> <chr> <chr>
        ##  1 audi         a4           1.8  1999     4 auto… f        18    29 p     comp…
        ##  2 audi         a4           1.8  1999     4 manu… f        21    29 p     comp…
        ##  3 audi         a4           2    2008     4 manu… f        20    31 p     comp…
        ##  4 audi         a4           2    2008     4 auto… f        21    30 p     comp…
        ##  5 audi         a4           2.8  1999     6 auto… f        16    26 p     comp…
        ##  6 audi         a4           2.8  1999     6 manu… f        18    26 p     comp…
        ##  7 audi         a4           3.1  2008     6 auto… f        18    27 p     comp…
        ##  8 audi         a4 quattro   1.8  1999     4 manu… 4        18    26 p     comp…
        ##  9 audi         a4 quattro   1.8  1999     4 auto… 4        16    25 p     comp…
        ## 10 audi         a4 quattro   2    2008     4 manu… 4        20    28 p     comp…
        ## # … with 224 more rows

2.  (Q4) *Make a scatterplot of hwy vs cyl.*

    ``` r
      ggplot(data = mpg) + 
      geom_point(mapping = aes(x = cyl, y = hwy))
    ```

    ![](report_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

#### Workflow: basics Exercises

1.  (Q2) *Tweak each of the following R commands so that they run
    correctly (`library(tidyverse)` is correct):*

``` r
library(tidyverse)
ggplot(dota = mpg) + 
  geom_point(mapping = aes(x = displ, y = hwy))

fliter(mpg, cyl = 8)

filter(diamond, carat > 3)
```

``` r
ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, y = hwy))
```

![](report_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

``` r
filter(mpg, cyl == 8)
```

    ## # A tibble: 70 × 11
    ##    manufacturer model      displ  year   cyl trans drv     cty   hwy fl    class
    ##    <chr>        <chr>      <dbl> <int> <int> <chr> <chr> <int> <int> <chr> <chr>
    ##  1 audi         a6 quattro   4.2  2008     8 auto… 4        16    23 p     mids…
    ##  2 chevrolet    c1500 sub…   5.3  2008     8 auto… r        14    20 r     suv  
    ##  3 chevrolet    c1500 sub…   5.3  2008     8 auto… r        11    15 e     suv  
    ##  4 chevrolet    c1500 sub…   5.3  2008     8 auto… r        14    20 r     suv  
    ##  5 chevrolet    c1500 sub…   5.7  1999     8 auto… r        13    17 r     suv  
    ##  6 chevrolet    c1500 sub…   6    2008     8 auto… r        12    17 r     suv  
    ##  7 chevrolet    corvette     5.7  1999     8 manu… r        16    26 p     2sea…
    ##  8 chevrolet    corvette     5.7  1999     8 auto… r        15    23 p     2sea…
    ##  9 chevrolet    corvette     6.2  2008     8 manu… r        16    26 p     2sea…
    ## 10 chevrolet    corvette     6.2  2008     8 auto… r        15    25 p     2sea…
    ## # … with 60 more rows

``` r
filter(diamonds, carat > 3)
```

    ## # A tibble: 32 × 10
    ##    carat cut     color clarity depth table price     x     y     z
    ##    <dbl> <ord>   <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
    ##  1  3.01 Premium I     I1       62.7    58  8040  9.1   8.97  5.67
    ##  2  3.11 Fair    J     I1       65.9    57  9823  9.15  9.02  5.98
    ##  3  3.01 Premium F     I1       62.2    56  9925  9.24  9.13  5.73
    ##  4  3.05 Premium E     I1       60.9    58 10453  9.26  9.25  5.66
    ##  5  3.02 Fair    I     I1       65.2    56 10577  9.11  9.02  5.91
    ##  6  3.01 Fair    H     I1       56.1    62 10761  9.54  9.38  5.31
    ##  7  3.65 Fair    H     I1       67.1    53 11668  9.53  9.48  6.38
    ##  8  3.24 Premium H     I1       62.1    58 12300  9.44  9.4   5.85
    ##  9  3.22 Ideal   I     I1       62.6    55 12545  9.49  9.42  5.92
    ## 10  3.5  Ideal   H     I1       62.8    57 12587  9.65  9.59  6.03
    ## # … with 22 more rows

## Google Colab

1.  *What are the URLs of your Google Colab notebooks (both Python and
    R)?*

    Link of python :
    <https://colab.research.google.com/drive/1iY3lFC7eIvharCE8CpzLHwp9jvXpMHhT?usp=sharing>

    Link of R :
    <https://colab.research.google.com/drive/1JCn35icq2F80MUGcZ9IdJKVqbTCko5EG?usp=sharing>

## Tableau

*Insert your the image of your final bar chart here* {r echo}
![tablue.jpeg](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/tablue.jpeg)

1.  *What conclusions can you draw from the chart?*

    In the graph we can see that west area has greater phone sales
    whereas south has highest sales in machines. The profit is negative.

## Observable and Vega-Lite

### A Taste of Observable

1.  *In the “New York City weather forecast” section, try replacing
    `Forecast: detailedForecast` with `Forecast: shortForecast`. Then
    press the blue play button or use Shift-Return to run your change.
    What happens?*

    If we change the forecast: detailedForecast with forecast:
    shortForecast, then it only shows small description or details of
    the weather.For example the description is changed to partly cloudy
    .

2.  *Under the scatterplot of temperature vs. name, try replacing
    `markCircle()` with `markSquare()`. Then press the blue play button
    or use Shift-Return to run your change. What happens? How about
    `markPoint()`?*

    If we try replacing markCircle() with markSquare() then the plots
    that were marked in circle will turn into square. If we change it
    into markPoint() then the square will turn into points.

3.  *Under “Pick a location, see the weather forecast”, pick a location
    on the map. Where was the point you picked near?*

    I picked longitude : -95.65 latitude : 38.14

4.  *The last visualization on this page is a “fancy” weather chart
    embedded from another notebook. Click on the 3 dots next to that
    chart and choose ‘Download PNG’. Insert the PNG into your report.*

![666](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/666.png)

### Charting with Vega-Lite

`markCircle()`

1.  *Pass an option of `{ size: 200 }` to `markCircle()`.*

    ![111](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/111.png)

2.  *Try `markSquare` instead of `markCircle`.*

![222!](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/222.png)

1.  *Try `markPoint({ shape: 'diamond' })`.*

![333](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/333.png)

`vl.x().fieldQ("Horsepower")`, …

1.  *Change `Horsepower` to `Acceleration`*

![444](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/444.png)

1.  *Swap what fields are displayed on the x- and y-axis*

![555](/Users/meghanagrandhi/Desktop/Data-Visualization-01237548-/Data-Visualization-01237548-/images/555.png)

`vl.tooltip().fieldN("Name")`

1.  *Change `Name` to `Origin`.*

    When we change a name to orgin country name is desplayed when you
    move the curser on graph.

Another example, `count()`

1.  *Remove the `vl.y().fieldN("Origin")` line.*

    When we hover the curser on the graph we cannot se any label.

2.  *Replace `count()` with `average("Miles_per_Gallon")`.*

    When you replace with average we can see average miles per gallon of
    a perticular country when we hover on it.

## References

*Every report must list the references that you consulted while
completing the assignment. If you consulted a webpage, you must include
the URL.*

    *Reference 1, https://r4ds.had.co.nz/workflow-basics.html#practice
    * Reference 2, https://colab.research.google.com/drive/165dTuQy5P7cgG8QqZMuLWP02LD9fLpLJ#scrollTo=qJAKN6380cJc
    * Reference 3, https://observablehq.com/@tomb/a-taste-of-observable
    * Reference 4, https://www.tableau.com/academic/students
    * Reference 5, https://r4ds.had.co.nz/workflow-basics.html#practice
    * Reference 6, https://colab.research.google.com/drive/165dTuQy5P7cgG8QqZMuLWP02LD9fLpLJ#scrollTo=s8aeChJ4_pgz.
