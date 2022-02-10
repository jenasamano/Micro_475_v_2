changing\_code\_on\_the\_composition
================

# Read in file and swap in new file name in code

``` r
library(readr)
KBH_94_23_DE_2_CPX_1 <- read_csv("KBH_94_23_DE_2_CPX_1.csv")
```

    ## Rows: 11 Columns: 14

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): P2O5, SiO2, TiO2, Al2O3, Cr2O3, MgO, CaO, MnO, FeO, NiO, Na2O, K2O
    ## lgl  (1): Total

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
View(KBH_94_23_DE_2_CPX_1)
```

\#Step 1

``` r
mol_numbers <- mutate(KBH_94_23_DE_2_CPX_1, P2O5/141.943,
                  SiO2/53.083,
                  TiO2/79.865,
                  Al2O3/101.961,
                  Cr2O3/99.993,
                  MgO/40.304,
                  CaO/56.077,
                  MnO/70.937,
                  FeO/71.844,
                  NiO/74.692,
                  Na2O/61.979,
                  K2O/94.195)
```

\#Step 2

``` r
oxygen_number <- mutate(mol_numbers, p = P2O5/141.943*5,
                        si = SiO2/53.083 * 2,
                        ti = TiO2/79.865 * 2,
                        al = Al2O3/101.961 * 3,
                        cr = Cr2O3/99.993 * 3,
                        mg = MgO/40.304 * 1,
                        ca = CaO/56.077 * 1,
                        mn = MnO/70.937 * 1,
                        fe = FeO/71.844 * 1,
                        ni = NiO/74.692 * 1,
                        na = Na2O/61.979 * 1,
                        k = K2O/94.195 * 1
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

## These are Pyroxenes so 6/the sum’d number from the sum\_row data

``` r
six_div_sum <- mutate(sum_row,norm_constant = 6/sum) %>% 
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
