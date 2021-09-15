Untitled
================

# Initializing

Adding the diamonds data set and naming it so we can use it later. put
data set first then pipe that to group function pipe that to
countfunction. Can use summarize function but the exercise is only
asking us to count.

``` r
diamond_project <- diamonds %>% 
  group_by(cut) %>% 
  count()
diamond_project
```

    ## # A tibble: 5 x 2
    ## # Groups:   cut [5]
    ##   cut           n
    ##   <ord>     <int>
    ## 1 Fair       1610
    ## 2 Good       4906
    ## 3 Very Good 12082
    ## 4 Premium   13791
    ## 5 Ideal     21551

## random sample of the row

using slice function to do this you can group by and pipe that to slice
to manipulate specific properties of my dataset

``` r
diamond_subset <- diamonds %>% 
  slice_sample(prop=0.01)
```

## Calculate average size

summary within a catagory need group by 100 largest in each category
subset dataframe to have 100 rows per catagory slice will help here too
instead of mean can use sd function to get the standard deviation mean
takes a list of numbers and returns a single value anything that makes
things a single value can be used in summary function (min, max,etc)
order by argument that slice max takes to pick which column to pick the
max from

``` r
diamond_question_3 <- diamonds %>% 
  group_by(clarity) %>% 
  slice_max(order_by=carat, n=100, with_ties = FALSE) %>% 
  summarise(mean_size=mean(carat))
diamond_question_3
```

    ## # A tibble: 8 x 2
    ##   clarity mean_size
    ##   <ord>       <dbl>
    ## 1 I1           2.51
    ## 2 SI2          2.62
    ## 3 SI1          2.30
    ## 4 VS2          2.23
    ## 5 VS1          2.10
    ## 6 VVS2         1.66
    ## 7 VVS1         1.51
    ## 8 IF           1.40

## part four to make some scatter plots

do not quote aes argument if it goes in aes i tell ggplot it is coming
from the dataset quotes means it is not coming from the dataset and is
coming from something else and the argument should not be in the aes
function if it is in the dataset it also goes in the aes argument for
example adding color to the carat output

``` r
diamond_plots_1 <- ggplot(data=diamonds,mapping=aes(x=x, y=y))+
  geom_point()
diamond_plots_1
```

![](hmwk_5_v_1_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

``` r
diamond_plot_2 <- ggplot(data=diamonds,mapping=aes(x=x, y=z))+
  geom_point()
diamond_plot_2
```

![](hmwk_5_v_1_files/figure-gfm/unnamed-chunk-4-2.png)<!-- -->

## removing questionable data

filter three times for each of the variables x,y,z in each filter
section can identify the bounds that I want to filter by piping removes
the need to id the dataset in the beginning of the filter function
filter is filtering things that I want I am not specifying what I don’t
want I am telling it what I do want

``` r
diamond_filter_1 <- diamonds %>% 
  filter(x>=3) %>% 
  filter(y>1 & y<20) %>% 
  filter(z>1 & z<10)
diamond_filter_1
```

    ## # A tibble: 53,917 x 10
    ##    carat cut       color clarity depth table price     x     y     z
    ##    <dbl> <ord>     <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
    ##  1  0.23 Ideal     E     SI2      61.5    55   326  3.95  3.98  2.43
    ##  2  0.21 Premium   E     SI1      59.8    61   326  3.89  3.84  2.31
    ##  3  0.23 Good      E     VS1      56.9    65   327  4.05  4.07  2.31
    ##  4  0.29 Premium   I     VS2      62.4    58   334  4.2   4.23  2.63
    ##  5  0.31 Good      J     SI2      63.3    58   335  4.34  4.35  2.75
    ##  6  0.24 Very Good J     VVS2     62.8    57   336  3.94  3.96  2.48
    ##  7  0.24 Very Good I     VVS1     62.3    57   336  3.95  3.98  2.47
    ##  8  0.26 Very Good H     SI1      61.9    55   337  4.07  4.11  2.53
    ##  9  0.22 Fair      E     VS2      65.1    61   337  3.87  3.78  2.49
    ## 10  0.23 Very Good H     VS1      59.4    61   338  4     4.05  2.39
    ## # ... with 53,907 more rows
