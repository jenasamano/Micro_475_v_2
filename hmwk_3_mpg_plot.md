homework\_3
================
jena
8/31/2021

########### 

I am adding the library command to the setup so it loads the tidyverse
with the setup. \#\#\#\#\#\#\#\#\#\#\#

############ 

lots of problems not sure why this wouldn’t make a bar graph my ufo
sightings data I will try to add my csv file for ufo sightings the
command is read.csv I put this under the library commands.Then you can
try adding the shape and duration plot once again.
\#\#\#\#\#\#\#\#\#\#\#

``` r
mpg_plot <- ggplot(data = mtcars, mapping = aes(x = cyl, y = mpg)) +
  geom_point()
print(mpg_plot)
```

![](hmwk_3_mpg_plot_files/figure-gfm/plot-1.png)<!-- -->
