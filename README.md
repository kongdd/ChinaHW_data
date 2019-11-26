
# Data of “Contributions of anthropogenic warming and urbanization to intensification of heatwaves over China”

## Figure1

`Figure1_data_(observed and modelled HW variation in 1961-2012).rda`

  - df\_sm: modelled HW characteristics. A data.table with the columns
    of: `scenario`, `type_TRS`, `variable`, `year`, `type_region`,
    `value`, `probs`, `index`, `model`, `mov`.
      - mov: 5 year moving average of HW characteristics
  - df\_HW.obs: A data.table with the columns of: `type_data`,
    `type_region`, `probs`, `year`, `type_TRS`, `variable`, `index`,
    `value`, `mov`

<!-- end list -->

``` r
load("data_Figure1_(observed and modelled HW variation in 1961-2012).rda")
df_sm
#                    scenario type_TRS variable year type_region     value
#      1: Historical + RCP4.5    his30      tas 1961       China 1.3288435
#      2: Historical + RCP4.5    his30      tas 1962       China 0.7845668
#      3: Historical + RCP4.5    his30      tas 1963       China 0.9051819
#      4: Historical + RCP4.5    his30      tas 1964       China 0.8306918
#      5: Historical + RCP4.5    his30      tas 1965       China 1.6105360
#     ---                                                                 
# 193352: Historical + RCP4.5       pi   tasmin 2008          WC 0.6097185
# 193353: Historical + RCP4.5       pi   tasmin 2009          WC 0.6262511
# 193354: Historical + RCP4.5       pi   tasmin 2010          WC 0.6107184
# 193355: Historical + RCP4.5       pi   tasmin 2011          WC 0.6426694
# 193356: Historical + RCP4.5       pi   tasmin 2012          WC 0.6102815
#         probs                         index     model       mov
#      1:  0.99             Probability ratio ACCESS1-0 1.0061974
#      2:  0.99             Probability ratio ACCESS1-0 0.9623210
#      3:  0.99             Probability ratio ACCESS1-0 1.0919640
#      4:  0.99             Probability ratio ACCESS1-0 1.0465337
#      5:  0.99             Probability ratio ACCESS1-0 1.0313631
#     ---                                                        
# 193352:  0.99 Fraction of attributable risk    inmcm4 0.6467697
# 193353:  0.99 Fraction of attributable risk    inmcm4 0.6382946
# 193354:  0.99 Fraction of attributable risk    inmcm4 0.6199278
# 193355:  0.99 Fraction of attributable risk    inmcm4 0.6224801
# 193356:  0.99 Fraction of attributable risk    inmcm4 0.6212231
df_HW.obs
#         type_data type_region  probs year type_TRS variable
#      1:     Urban          EC 0.9000 1961       pi      tas
#      2:     Urban          EC 0.9000 1962       pi      tas
#      3:     Urban          EC 0.9000 1963       pi      tas
#      4:     Urban          EC 0.9000 1964       pi      tas
#      5:     Urban          EC 0.9000 1965       pi      tas
#     ---                                                    
# 181436:       ALL       China 0.9999 2012    his30   tasmin
# 181437:       ALL       China 0.9999 2013    his30   tasmin
# 181438:       ALL       China 0.9999 2014    his30   tasmin
# 181439:       ALL       China 0.9999 2015    his30   tasmin
# 181440:       ALL       China 0.9999 2016    his30   tasmin
#                                 index     value       mov
#      1: Maximum annual intensity (°C) 5.4090639 5.0451092
#      2: Maximum annual intensity (°C) 4.8205769 5.0708869
#      3: Maximum annual intensity (°C) 4.9056869 5.0592252
#      4: Maximum annual intensity (°C) 5.1482197 5.0887896
#      5: Maximum annual intensity (°C) 5.0125785 5.2093082
#     ---                                                  
# 181436: Fraction of attributable risk 0.9429081 0.9562599
# 181437: Fraction of attributable risk 0.9664654 0.9532441
# 181438: Fraction of attributable risk 0.9493167 0.9593867
# 181439: Fraction of attributable risk 0.9636990 0.9635064
# 181440: Fraction of attributable risk 0.9745445 0.9625201
```

## Figure2

`data_Figure2_ECOF.rda`

  - d\_coef: regression coefficients of finger print
  - d\_cont: attributable change to each factor

<!-- end list -->

``` r
load("data_Figure2_ECOF.rda")
d_cont
#      type_TRS varname    index type_signal  method variable    betalow
#   1:    pi200     tas duration         one     ols      OBS 3.19806794
#   2:    pi200     tas duration         one     ols    Urban 0.82661902
#   3:    pi200     tas duration         one     ols      ALL 2.37144892
#   4:    pi200     tas duration         one     ols      GHG 3.79484509
#   5:    pi200     tas duration         one     ols      NAT 0.58454205
#  ---                                                                  
# 716:    his30  tasmin      FAR         two tls.ROF      OBS 0.79430438
# 717:    his30  tasmin      FAR         two tls.ROF    Urban 0.16527514
# 718:    his30  tasmin      FAR         two tls.ROF      ALL 0.62902924
# 719:    his30  tasmin      FAR         two tls.ROF      GHG 0.47129538
# 720:    his30  tasmin      FAR         two tls.ROF      NAT 0.07199643
#        betahat    betaup
#   1: 5.6974256 7.5578589
#   2: 1.4726392 1.9535138
#   3: 4.2247864 5.6043451
#   4: 4.8408242 5.8868033
#   5: 0.8567600 1.1289780
#  ---                    
# 716: 1.0105963 1.2241073
# 717: 0.2102801 0.2547065
# 718: 0.8003161 0.9694007
# 719: 0.7045844 0.9322955
# 720: 0.2048966 0.3568982
d_coef
#      type_TRS varname    index type_signal  method variable   betalow
#   1:    pi200     tas duration         one     ols      ALL 0.7562062
#   2:    pi200     tas duration         one     ols      GHG 0.2941362
#   3:    pi200     tas duration         one     ols      NAT 1.1907241
#   4:    pi200     tas duration         one tls.ROF      ALL 0.7190999
#   5:    pi200     tas duration         one tls.ROF      GHG 0.3009815
#  ---                                                                 
# 356:    his30  tasmin      FAR         one tls.ROF      NAT 2.7784679
# 357:    his30  tasmin      FAR         two     ols      GHG 0.6521218
# 358:    his30  tasmin      FAR         two     ols      NAT 0.7911056
# 359:    his30  tasmin      FAR         two tls.ROF      GHG 0.6654469
# 360:    his30  tasmin      FAR         two tls.ROF      NAT 0.4140761
#        betahat    betaup sd df2
#   1: 0.9105414 1.0648766 NA  31
#   2: 0.3752095 0.4562827 NA  31
#   3: 1.7452377 2.2997512 NA  31
#   4: 0.9204575 1.1243472 NA  31
#   5: 0.4010220 0.5020558 NA  31
#  ---                           
# 356: 3.7421670 5.1460374 NA  29
# 357: 0.8834503 1.1147788 NA  29
# 358: 1.3777449 1.9643842 NA  29
# 359: 0.9948400 1.3163574 NA  29
# 360: 1.1784306 2.0526437 NA  29
```

## Figure 3

`data_Figure3_HW at different warming levels.rda`

``` r
load("data_Figure3_HW at different warming levels.rda")
df
#          variable            scenario      model year      Tinc      value
#       1:      tas Historical + RCP2.6 bcc-csm1-1 1850 0.1426438 34.1684611
#       2:      tas Historical + RCP2.6 bcc-csm1-1 1850 0.1426438 14.6779325
#       3:      tas Historical + RCP2.6 bcc-csm1-1 1850 0.1426438  6.1640783
#       4:      tas Historical + RCP2.6 bcc-csm1-1 1850 0.1426438  2.1839739
#       5:      tas Historical + RCP2.6 bcc-csm1-1 1850 0.1426438  1.0759046
#      ---                                                                  
# 3362996:   tasmin Historical + RCP8.5  NorESM1-M 2100 6.1307237  0.9862678
# 3362997:   tasmin Historical + RCP8.5  NorESM1-M 2100 6.1307237  0.9938041
# 3362998:   tasmin Historical + RCP8.5  NorESM1-M 2100 6.1307237  0.9966069
# 3362999:   tasmin Historical + RCP8.5  NorESM1-M 2100 6.1307237  0.9981461
# 3363000:   tasmin Historical + RCP8.5  NorESM1-M 2100 6.1307237  0.9991694
#            probs                         index
#       1: 0.90000   Annual mean duration (days)
#       2: 0.95000   Annual mean duration (days)
#       3: 0.97500   Annual mean duration (days)
#       4: 0.99000   Annual mean duration (days)
#       5: 0.99500   Annual mean duration (days)
#      ---                                      
# 3362996: 0.99750 Fraction of attributable risk
# 3362997: 0.99900 Fraction of attributable risk
# 3362998: 0.99950 Fraction of attributable risk
# 3362999: 0.99975 Fraction of attributable risk
# 3363000: 0.99990 Fraction of attributable risk
```

## Figure 4

`data_Figure4_PR_spatial.rda`

``` r
load("data_Figure4_PR_spatial.rda")
df
#          I variable index       0.85          1.5          2        3.5
#    1:    1      tas    PR 11.8112655 27.851467117 42.6487437 79.5373699
#    2:    2      tas    PR 11.9362199 27.999771893 42.8144177 81.5655377
#    3:    3      tas    PR  8.6032363 20.068307004 31.3645470 67.5387050
#    4:    4      tas    PR  4.8770281 10.449163421 15.8616356 36.2810479
#    5:    5      tas    PR  3.9856350  7.463865252 10.5538627 21.3977257
#   ---                                                                  
# 7610: 1265   tasmin   FAR -0.2420542  0.086325422  0.2683950  0.6055277
# 7611: 1266   tasmin   FAR -0.2157345  0.086418312  0.2394154  0.5851450
# 7612: 1267   tasmin   FAR -0.2300216  0.075472814  0.2047545  0.5794628
# 7613: 1268   tasmin   FAR -0.2882128  0.004501465  0.1662336  0.5619165
# 7614: 1269   tasmin   FAR -0.3224780 -0.038802676  0.1250093  0.5251116
str(poly_clip, 2)
# Formal class 'SpatialPolygonsDataFrame' [package "sp"] with 5 slots
#   ..@ data       :'data.frame':   1407 obs. of  4 variables:
#   ..@ polygons   :List of 1407
#   ..@ plotOrder  : int [1:1407] 1287 1231 1031 1221 911 1124 1401 1036 919 891 ...
#   ..@ bbox       : num [1:2, 1:2] 73.4 15.1 135.1 53.6
#   .. ..- attr(*, "dimnames")=List of 2
#   ..@ proj4string:Formal class 'CRS' [package "sp"] with 1 slot
```

How to visualize `df`?

``` r
d_param <- expand.grid(varname = varnames, indice = unique(df$index))[1, ]
temp <- foreach(varname = d_param$varname, indice = d_param$indice,  i = icount(1)) %do% {
    d <- df[variable == varname & index == indice, .SD, .SDcols = as.character(Tinc)] %>% 
        set_colnames(paste0("x", colnames(.)))
    
    scale_factor = ifelse(indice == "FAR", 100, 1)
    unit         = ifelse(indice == "FAR", "%", "")
    
    poly_clip@data <- data.frame(d[info_clip$id, ])*scale_factor
    p <- plot_FPAR(poly_clip, indice, varname, 
                   stat = list(show = FALSE, name=as.character(indice), loc = c(104, 45)),
                   unit = unit,
                   unit.adj = 0.45,
                   show = FALSE,
                   sp.layout = sp_arc_CH.south) # NULL, sp_arc_CH.south
}
```
