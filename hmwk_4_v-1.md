Some math AKA Homework 4
================

# Homework 4

Homework 4 writing script to do some simple math equations and learning
to use functions and make these functions a plot. \#

## Calculting the sum

assigning a value to an object and adding two objects together \#\#

``` r
a <- 3
b <- 2
print(a+b)
```

    ## [1] 5

\#\#\#Sum function \#\#\#

``` r
sum(2,3)
```

    ## [1] 5

\#\#\#**Flights** The code for the library addition might still be in my
script I have issues correlating what I write in code with the result.
This extra step lets me see the code and see the result together. This
next step will add a plot to the code written thus far. \#\#\#

``` r
AA_flights <- filter(flights, carrier == "AA")
```

flights is a data set inside the data frame nyc flights.

``` r
ggplot(data= AA_flights, mapping = aes(x=dep_delay, y=arr_delay))+
  geom_point()
```

    ## Warning: Removed 782 rows containing missing values (geom_point).

![](hmwk_4_v-1_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->