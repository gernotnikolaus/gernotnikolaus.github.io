---
layout: default
title: "Projected Heat Exposure for Elderly Populations in Southwestern Europe under Future Climate Scenarios"
date: 2026-03-29
categories: [projects]
permalink: /projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope
---

August 2025 was the third-warmest August on record globally; Heatwaves are becoming increasingly frequent and intense in Southwestern Europe [1]. Using NASA/NEX-GDDP [2] climate models (MIROC5, GFDL-CM3, HadGEM2-ES), EUROSTAT demographic projections [3], I analyzed the future exposure for elderly populations in Portugal, Spain, and France to summer heat under different climate scenarios (current, RCP4.5, and RCP8.5).

In GEE, I calculated the summer mean temperature for Portugal, Spain, and France under current and future projections (RCP4.5 and RCP8.5) and aggregated the data at NUTS3 level (sub-regional administrative units in the EU) using zonal statistics. Outputs were exported for further analysis in R (sf, dplyr, ggplot2) and prepared for mapping in QGIS.

<div class="blog-image">
  <img src="{{ '/assets/images/projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope/TemperatureMaps_GernotNikolaus.png' | relative_url }}" alt="Mean Summer Temperature in Southwestern Europe (own figure)">
  <figcaption>Figure 1: Mean Summer Temperature in Southwestern Europe (own figure).</figcaption>
</div>

Figure 1 shows the distribution of summer temperatures in Southwestern Europe. While Portugal and especially Spain already have the highest baseline temperatures, these regions are projected to experience the largest increases. Southern and inland Spain (e.g., Córdoba, Sevilla, Ciudad Real, Badajoz) are expected to reach mean summer temperatures of 36–37°C (Table 1), with temperature increases up to 5°C (Figure 2-3). Portugal’s Alentejo region will also warm significantly (~33–34°C), while France experiences moderate warming (~28–31°C), the temperature increase is still high.

<div class="blog-image">
  <img src="{{ '/assets/images/projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope/delta_GernotNikolaus.png' | relative_url }}" alt="Projected Summer Temperature Increase in Southwestern Europe (ΔT) 2050 (own figure)">
  <figcaption>Figure 2: Projected Summer Temperature Increase in Southwestern Europe (ΔT) 2050 (own figure).</figcaption>
</div>

<div class="blog-image">
  <img src="{{ '/assets/images/projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope/temperatureDistribution_GernotNikolaus.png' | relative_url }}" alt="Distribution of Summer Temperatures in Southwestern Europe (own figure)">
  <figcaption>Figure 3: Distribution of Summer Temperatures in Southwestern Europe (own figure).</figcaption>
</div>

While the elderly share 2025 is quite even in the countries, Spain will have an increasing elderly grow in northwestern and inland regions by 2050 (Figure 4). Regions such as Zamora, León, and Asturias are projected to see elderly shares rise to 43–47%. Portugal shows moderate increases in elderly share, while France remains comparatively stable (Table 1, shows only top 10 NUTS3).

<div class="blog-image">
  <img src="{{ '/assets/images/projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope/Elderly_GernotNikolaus.png' | relative_url }}" alt="Elderly share (65+) 2025 vs 2050 (own figure)">
  <figcaption>Figure 4: Elderly share (65+) 2025 vs 2050 (own figure).</figcaption>
</div>

Figure 5 shows elderly population shares. The overall trend is a clear rightward shift across all three countries, indicating that older individuals will represent a much larger portion of the total population by 2050. While France and Spain have higher density peaks in 2050, Spain is more varied across regions.

<div class="blog-image">
  <img src="{{ '/assets/images/projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope/Elderly_Share_by_Country_GernotNikolaus.png' | relative_url }}" alt="Distribution of Elderly Population Share by Country (own figure)">
  <figcaption>Figure 5: Distribution of Elderly Population Share by Country (own figure).</figcaption>
</div>

Figure 6 shows a bivariate map, visualizing delta8.5 and share of elderly Population by 2050. This map shows patterns to identify regions of highest vulnerability. Spain’s inland provinces, such as Zamora, Cáceres, and Ciudad Real, have the highest combined exposure due to both high temperatures and a large proportion of elderly residents. While Portugal shows moderate combined exposure, France’s regions, while temperature increases, have lower elderly shares and thus lower exposure overall (compare with Figure 5).

<div class="blog-image">
  <img src="{{ '/assets/images/projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope/bivariateMap_delta85_elderly2050_GernotNikolaus.png' | relative_url }}" alt="Temperature Increase and Elderly Population Share (2050, RCP8.5) (own figure)">
  <figcaption>Figure 6: Temperature Increase and Elderly Population Share (2050, RCP8.5) (own figure).</figcaption>
</div>

Table 1 lists the top 30 NUTS3 regions by combined exposure, highlighting Spain’s dominance in regions most at risk. The combined exposure indicator was calculated by normalizing projected summer temperature (RCP8.5) and elderly population share (2050) to a 0–1 scale and summing both variables. Only the top 30 regions are displayed here for clarity. The full dataset includes 170 NUTS3 regions across Portugal, Spain, and France.
  
| NUTS_NAME.x               | COUNTRY | ELDERLY_SHARE_2025 | ELDERLY_SHARE_2050 | TEMP_base | TEMP_rcp45 | TEMP_rcp85 | DELTA_45 | DELTA_85 | Combined_Exposure |
|---------------------------|---------|--------------------|--------------------|-----------|------------|------------|----------|----------|-------------------|
| Zamora                    | ES      | 0,33               | 0,47               | 26,97     | 30,84      | 31,65      | 3,87     | 4,68     | 1,61              |
| Cáceres                   | ES      | 0,26               | 0,40               | 30,50     | 34,64      | 35,69      | 4,14     | 5,19     | 1,59              |
| Ciudad Real               | ES      | 0,23               | 0,39               | 31,83     | 35,76      | 36,82      | 3,93     | 4,99     | 1,59              |
| Córdoba                   | ES      | 0,22               | 0,36               | 32,84     | 36,56      | 37,56      | 3,72     | 4,72     | 1,52              |
| Badajoz                   | ES      | 0,22               | 0,36               | 32,02     | 35,97      | 37,00      | 3,95     | 4,98     | 1,51              |
| Jaén                      | ES      | 0,22               | 0,36               | 32,37     | 35,86      | 36,82      | 3,49     | 4,44     | 1,49              |
| Salamanca                 | ES      | 0,29               | 0,42               | 27,65     | 31,84      | 32,81      | 4,20     | 5,17     | 1,48              |
| Alto Alentejo             | PT      | 0,29               | 0,39               | 29,58     | 33,19      | 33,95      | 3,60     | 4,37     | 1,40              |
| Cuenca                    | ES      | 0,24               | 0,38               | 29,34     | 33,19      | 34,11      | 3,85     | 4,77     | 1,39              |
| Toledo                    | ES      | 0,20               | 0,35               | 30,97     | 35,11      | 36,15      | 4,14     | 5,18     | 1,38              |
| Alentejo Central          | PT      | 0,28               | 0,39               | 29,22     | 32,55      | 33,22      | 3,32     | 4,00     | 1,37              |
| Ávila                     | ES      | 0,28               | 0,41               | 26,21     | 30,41      | 31,40      | 4,20     | 5,19     | 1,36              |
| Albacete                  | ES      | 0,21               | 0,37               | 30,23     | 33,57      | 34,45      | 3,34     | 4,22     | 1,35              |
| Sevilla                   | ES      | 0,19               | 0,33               | 32,50     | 35,94      | 36,78      | 3,44     | 4,29     | 1,35              |
| Beira Baixa               | PT      | 0,31               | 0,38               | 28,70     | 32,51      | 33,34      | 3,81     | 4,64     | 1,35              |
| Valladolid                | ES      | 0,26               | 0,40               | 27,23     | 31,13      | 31,95      | 3,90     | 4,71     | 1,34              |
| Beiras e Serra da Estrela | PT      | 0,31               | 0,39               | 26,78     | 30,70      | 31,57      | 3,92     | 4,79     | 1,27              |
| Terras de Trás-os-Montes  | PT      | 0,32               | 0,38               | 27,15     | 31,03      | 31,87      | 3,87     | 4,72     | 1,23              |
| Soria                     | ES      | 0,27               | 0,39               | 26,43     | 30,33      | 31,19      | 3,91     | 4,77     | 1,22              |
| Segovia                   | ES      | 0,25               | 0,39               | 26,13     | 30,24      | 31,15      | 4,11     | 5,02     | 1,22              |
| Huelva                    | ES      | 0,19               | 0,33               | 30,49     | 33,73      | 34,47      | 3,24     | 3,98     | 1,21              |
| León                      | ES      | 0,30               | 0,44               | 23,16     | 26,46      | 27,06      | 3,30     | 3,90     | 1,19              |
| Zaragoza                  | ES      | 0,23               | 0,35               | 28,49     | 32,35      | 33,18      | 3,86     | 4,69     | 1,18              |
| Teruel                    | ES      | 0,26               | 0,37               | 26,77     | 30,55      | 31,43      | 3,79     | 4,66     | 1,17              |
| Ourense                   | ES      | 0,32               | 0,42               | 24,03     | 27,30      | 27,91      | 3,27     | 3,88     | 1,17              |
| Granada                   | ES      | 0,20               | 0,34               | 29,70     | 32,78      | 33,62      | 3,08     | 3,93     | 1,16              |
| Região de Coimbra         | PT      | 0,28               | 0,38               | 26,74     | 30,19      | 30,84      | 3,46     | 4,10     | 1,16              |
| Douro                     | PT      | 0,27               | 0,38               | 26,19     | 30,06      | 30,90      | 3,87     | 4,71     | 1,16              |
| Cádiz                     | ES      | 0,19               | 0,34               | 29,09     | 32,24      | 32,90      | 3,15     | 3,81     | 1,15              |
| Palencia                  | ES      | 0,29               | 0,41               | 24,12     | 27,57      | 28,20      | 3,45     | 4,08     | 1,15              |


<div class="blog-image">
  <figcaption>Table 1: Top 30 NUTS3 regions in Southwestern Europe by combined heat and elderly exposure (2050, RCP8.5).</figcaption>
</div>

This study is intended for academic purposes only. It has not been peer-reviewed, and no formal uncertainty analysis was performed.

[1] https://climate.copernicus.eu/major-heatwave-southwestern-europe-during-third-warmest-august-record
[2] Thrasher, B., et al. (2012). "Technical Note: Bias correcting climate model simulated daily temperature extremes with quantile mapping," Hydrology and Earth System Sciences, 16(9), 3309-3314
[3] https://doi.org/10.2908/PROJ_19RP3 [28.03.2026]
