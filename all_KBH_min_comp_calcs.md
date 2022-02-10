KBH\_94\_23\_DE\_7\_Ol\_1
================

``` r
library(readr)
file_names <- list.files(pattern = "KBH_94_23_DE[0-9A-Za-z_]+.csv")
data_list <- map(file_names, ~read_csv(.x))
```

    ## Rows: 10 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 11 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 15 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 9 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 26 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 14 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 11 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 8 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## dbl (13): point, phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, ma...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 9 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## dbl (13): point, phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, ma...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 27 Columns: 25

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## dbl (25): point, phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, ma...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 34 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 20 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 12 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 16 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 10 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 13 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 20 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 10 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 11 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 25 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

    ## Rows: 15 Columns: 13

    ## -- Column specification --------------------------------------------------------
    ## Delimiter: ","
    ## chr  (1): point
    ## dbl (12): phos_ox, sil_ox, tit_ox, alu_ox, cro_ox, mag_ox, cal_ox, man_ox, f...

    ## 
    ## i Use `spec()` to retrieve the full column specification for this data.
    ## i Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
names(data_list) <- file_names
```

``` r
mol_numbers <- map(data_list, ~mutate(.x, phos_ox/141.943,
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
                  pot_ox/94.195))

oxygen_number <- map(mol_numbers, ~mutate(.x , p = phos_ox/141.943*5,
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
                        ))

sum_ox <- map(oxygen_number, ~select(.x , p,
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
                   ))

sum_row <- map(sum_ox, function(.x) {
  .x %>% 
  mutate(sum = rowSums(.))})
num_ox <- c(6,6,4,6,4,6,6,4,4,6,6,4,4,6,6,4,6,6,6,4,6)# make sure this matches the data order must be in the same order that it appears in the list.
six_div_sum <- map2(sum_row, num_ox, function(.x,.y){
  mutate(.x,norm_constant = .y/sum) %>% 
  select(norm_constant)})

six_div_sum_oxygen_number <- map2(oxygen_number, six_div_sum, ~bind_cols(.x,.y))

oxy_num_mult_norm_const <- map(six_div_sum_oxygen_number, ~mutate(.x, a = p*norm_constant,
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
                                  ))

mult_cations <- map(oxy_num_mult_norm_const, ~mutate(.x, a1 = a * 2/5,
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
                       a12 = l * 2/1))

end <- map_dfr(mult_cations, function(.x){ 
  .x %>% 
      summarise(ave_P = mean(a1,na.rm = TRUE),
            ave_Si = mean(a2, na.rm = TRUE),
            ave_Ti = mean(a3, na.rm = TRUE),
            ave_Al = mean(a4, na.rm = TRUE),
            ave_Cr = mean(a5, na.rm = TRUE),
            ave_Mg = mean(a6, na.rm = TRUE),
            ave_Ca = mean(a7, na.rm = TRUE),
            ave_Mn = mean(a8, na.rm = TRUE),
            ave_Fe = mean(a9, na.rm = TRUE),
            ave_Ni = mean(a10, na.rm = TRUE),
            ave_Na = mean(a11, na.rm = TRUE),
            ave_K = mean(a12, na.rm = TRUE) 
            )}) %>% 
  mutate(file_names = file_names)
```

``` r
write_csv(end,"PYX_and_Ol_min_comp_calc.csv")
```
