# Global subnational income data

### Overview

This dataset provides GDP per capita data over 1992-2013 at the subnational level globally. Previous data sets of subnational GDP had limited spatial coverage and data availability tended to be biased towards higher-income regions. For our publication "Globally unequal effect of extreme heat on economic growth" in _Science Advances_ (10.1126/sciadv.add3726), Justin Mankin and I produced a globally consistent set of subnational GDP per capita data by downscaling country-level GDP data using nightlights data. These data can be used to explore patterns of global development and economic production at the subnational level.

If using this data, please cite the _Science Advances_ paper (doi forthcoming).

### Methodology

This methodology is outlined in more detail in the paper (doi forthcoming). In brief, we regressed observed subnational GDP per capita from the [DOSE dataset](https://zenodo.org/record/4681306#.YxnlI-xByDU) onto country-level GDP per capita from the [World Bank World Development Indicators](https://databank.worldbank.org/source/world-development-indicators) and region-average nighttime luminosity from the [DMSP-OLS satellite system](https://eogdata.mines.edu/products/dmsp/). This regression yields parameters that tell us how regional GDP per capita changes when country-level GDP per capita changes as well as the within-country spatial distribution of that income (using nightlights). We then use the country-level GDP per capita and nightlights data to predict regional GDP per capita in regions where those data were not originally available.

The model using country-level GDP per capita and nightlights effectively predicted regional GDP per capita in-sample, with R-squared values approaching 0.9. A series of out-of-sample cross-validation tests demonstrated that the model also has low out-of-sample error. Our parsimonious statistical model also outperformed more complex models using predictors such as regional area and regional crop yields in these cross-validation tests.

We estimate uncertainty in these regional GDP per capita data by resampling the regression parameters and adding realizations of random noise. The dataset provided here is the average and standard deviation of our predicted GDP per capita values across these uncertainty samples for each year and subnational region.

Analysis code used to produce this data is available in the [replication code from the paper](https://github.com/ccallahan45/CallahanMankin_ExtremeHeatEconomics_2022). 
