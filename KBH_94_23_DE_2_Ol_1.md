KBH\_94\_23\_DE\_2\_Ol\_1
================

``` r
library(readr)
KBH_94_23_DE_2_Ol_1 <- read_csv("KBH_94_23_DE_2_Ol_1.csv")
```

    ## Rows: 15 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
View(KBH_94_23_DE_2_Ol_1)
```

\#Step 1

``` r
mol_numbers <- mutate(KBH_94_23_DE_2_Ol_1, phos_ox/141.943,
                  sil_ox/53.083,
                  tit_ox/79.865,
                  alu_ox/101.961,
                  cro_ox/99.993,
                  mag_ox/40.304,
                  cal_ox/56.077,
                  man_ox/70.937,
                  fer_ox/71.844,
                  nic_ox/74.692,
                  sod_ox/61.979,
                  pot_ox/94.195)
```

\#Step 2

``` r
oxygen_number <- mutate(mol_numbers, p = phos_ox/141.943*5,
                        si = sil_ox/53.083 * 2,
                        ti = tit_ox/79.865 * 2,
                        al = alu_ox/101.961 * 3,
                        cr = cro_ox/99.993 * 3,
                        mg = mag_ox/40.304 * 1,
                        ca = cal_ox/56.077 * 1,
                        mn = man_ox/70.937 * 1,
                        fe = fer_ox/71.844 * 1,
                        ni = nic_ox/74.692 * 1,
                        na = sod_ox/61.979 * 1,
                        k = pot_ox/94.195 * 1
                        )
```

# isolate

``` r
sum_ox <- select(oxygen_number, p,
                   si,
                   ti,
                   al,
                   cr,
                   mg,
                   ca,
                   mn,
                   fe,
                   ni,
                   na,
                   k
                   )
```

``` r
sum_row <- sum_ox %>% 
  mutate(sum = rowSums(.))
```

## These are Olivines so 4/the sum???d number from the sum\_row data

``` r
six_div_sum <- mutate(sum_row,norm_constant = 4/sum) %>% 
  select(norm_constant)
```

# Step 3

``` r
six_div_sum_oxygen_number <- bind_cols(oxygen_number,six_div_sum)
```

# Math

``` r
oxy_num_mult_norm_const <- mutate(six_div_sum_oxygen_number, a = p*norm_constant,
                                  b = si*norm_constant,
                                  c = ti*norm_constant,
                                  d = al*norm_constant,
                                  e = cr*norm_constant,
                                  f = mg*norm_constant,
                                  g = ca*norm_constant,
                                  h = mn*norm_constant,
                                  i = fe*norm_constant,
                                  j = ni*norm_constant,
                                  k = na*norm_constant,
                                  l = k*norm_constant
                                  )
```

\#Step 4

``` r
mult_cations <- mutate(oxy_num_mult_norm_const, a1 = a * 2/5,
                       a2 = b * 1/2,
                       a3 = c * 1/2,
                       a4 = d * 2/3,
                       a5 = e * 2/3,
                       a6 = f * 1/1,
                       a7 = g * 1/1,
                       a8 = h * 1/1,
                       a9 = i * 1/1,
                       a10 = j * 1/1,
                       a11 = k * 2/1,
                       a12 = l * 2/1)
```

\#Sum up

``` r
end <- mult_cations %>% 
  summarise(ave_P = mean(a1),
            ave_Si = mean(a2),
            ave_Ti = mean(a3),
            ave_Al = mean(a4),
            ave_Cr = mean(a5),
            ave_Mg = mean(a6),
            ave_Ca = mean(a7),
            ave_Mn = mean(a8),
            ave_Fe = mean(a9),
            ave_Ni = mean(a10),
            ave_Na = mean(a11),
            ave_K = mean(a12) 
            )
```
