Pllng\_in\_csv\_manpltng
================

``` r
petro_lab_4 <- read_csv("petro_lab_4.csv")
```

    ## Rows: 10 Columns: 11

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): name
    ## dbl (10): MnO, FeO, K2O, CaO, TiO2, Na2O, MgO, Al2O3, SiO2, Total

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
CaO_FeO_lines <- data.frame(
  xstart=c(7.43,   23.95,  .24), 
  ystart=c(21.23,  0,     11.76),
  xend=c(  23.95,  .24,    7.43),
  yend=c(  0,      11.76, 21.23)
)
```

``` r
CaO_FeO_data <- petro_lab_4 %>%
  filter(name %in% c("Syenite", "Gabbro", "Cpx", "Pl^2", "Ol")) %>% 
  mutate(CaO_FeO_color=as.factor(c(1,2,3,3,3)))
```

``` r
CaO_FeO_Plot <-
  ggplot()+
  geom_point(data=CaO_FeO_data, aes(x = FeO, y = CaO, color=CaO_FeO_color))+
  geom_segment(data=CaO_FeO_lines, aes(x=xstart, y=ystart, xend=xend, yend=yend))+
  theme_classic()+
    labs(x="Iron Oxide", y="Calcium Oxide")+
  annotate("text", x=0, y=14, label="Pl")+
  annotate("text",x=8, y=25, label= "Cpx")+
  annotate("text",x=24, y=3, label= "Ol")+
  annotate("text",x=10, y=13, label= "Gabbro")+
  annotate("text",x=4, y=5, label= "Syenite")
CaO_FeO_Plot
```

![](Pllng_in_csv_manpltng_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

``` r
CaO_SiO2_lines <- data.frame(
  xstart=c(37.54,50.95,53.19), 
  ystart=c(0,    21.23,11.76),
  xend=c(  50.95,53.19,37.54),
  yend=c(  21.23,11.76,0)
)
```

``` r
CaO_SiO2_data <- petro_lab_4 %>%
  filter(name %in% c("Syenite", "Gabbro", "Cpx", "Pl^2", "Ol")) %>% 
  mutate(CaO_SiO2_color=as.factor(c(1,2,3,3,3)))
```

``` r
CaO_SiO2_Plot <-
  ggplot()+
  geom_point(data=CaO_SiO2_data, aes(x = SiO2, y = CaO, color=CaO_SiO2_color))+
  geom_segment(data=CaO_SiO2_lines, aes(x=xstart, y=ystart, xend=xend, yend=yend))+
  theme_classic()+
  labs(x="Silica Oxide", y="Calcium Oxide")+
  annotate("text", x=55, y=12, label="Pl")+
  annotate("text",x=50, y=25, label= "Cpx")+
  annotate("text",x=37, y=3, label= "Ol")+
  annotate("text",x=47, y=13, label= "Gabbro")+
  annotate("text",x=59, y=5, label= "Syenite")
CaO_SiO2_Plot
```

![](Pllng_in_csv_manpltng_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

``` r
Al2O3_MgO_lines <- data.frame(
  xstart=c(0,15.39,38.07), 
  ystart=c(29.45, 3.19,0),
  xend=c(  15.39,38.07,0),
  yend=c(  3.19,0,29.45)
)
```

``` r
Al2O3_MgO_data <- petro_lab_4 %>%
  filter(name %in% c("Syenite", "Gabbro", "Cpx", "Pl^2", "Ol")) %>% 
  mutate(Al2O3_MgO_color=as.factor(c(1,2,3,3,3)))
```

``` r
Al2O3_MgO_Plot <-
  ggplot()+
  geom_point(data=Al2O3_MgO_data, aes(x = MgO, y = Al2O3, color=Al2O3_MgO_color))+
  geom_segment(data=Al2O3_MgO_lines, aes(x=xstart, y=ystart, xend=xend, yend=yend))+
  theme_classic()+
  labs(x="Magnesium Oxide", y="Aluminium Oxide")+
  annotate("text", x=0, y=34, label="Pl")+
  annotate("text",x=15, y=1, label= "Cpx")+
  annotate("text",x=40, y=1, label= "Ol")+
  annotate("text",x=16, y=18, label= "Gabbro")+
  annotate("text",x=3, y=14, label= "Syenite")
Al2O3_MgO_Plot
```

![](Pllng_in_csv_manpltng_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->
