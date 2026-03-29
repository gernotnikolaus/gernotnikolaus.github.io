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

Table 1 lists the top 50 NUTS3 regions by combined exposure, highlighting Spain’s dominance in regions most at risk. Only the top 20 regions are displayed here for clarity. The full dataset includes 170 NUTS3 regions across Portugal, Spain, and France.
  
  | Rank | Region | Country | Temp RCP8.5 (°C) | Elderly Share 2050 | Combined Exposure |
  |------|--------|--------|-----------------|------------------|-----------------|
  | 1    | Zamora | ES     | 31.65           | 0.47             | 1.61            |
  | 2    | Cáceres | ES    | 35.69           | 0.40             | 1.59            |
  | 3    | Ciudad Real | ES | 36.82           | 0.39             | 1.59            |
  | 4    | Salamanca | ES   | 32.81           | 0.42             | 1.48            |
  | 5    | Ávila | ES      | 31.40           | 0.41             | 1.36            |
  | 6    | Alentejo Central | PT | 33.22      | 0.39             | 1.37            |
  | 7    | Alto Alentejo | PT | 33.95         | 0.39             | 1.40            |
  | 8    | Cuenca | ES     | 34.11           | 0.38             | 1.39            |
  | 9    | Valladolid | ES  | 31.95           | 0.40             | 1.34            |
  | 10   | Beira Baixa | PT  | 33.34           | 0.38             | 1.35            |
  | 11   | Albacete | ES   | 34.45           | 0.37             | 1.35            |
  | 12   | Asturias | ES   | 24.82           | 0.43             | 0.99            |
  | 13   | León | ES       | 27.06           | 0.44             | 1.19            |
  | 14   | Ourense | ES    | 27.91           | 0.42             | 1.17            |
  | 15   | Soria | ES      | 31.19           | 0.39             | 1.22            |
  | 16   | Segovia | ES    | 31.15           | 0.39             | 1.22            |
  | 17   | Pontevedra | ES | 26.53           | 0.40             | 0.97            |
  | 18   | Burgos | ES     | 28.18           | 0.40             | 1.07            |
  | 19   | Cantabria | ES  | 24.90           | 0.39             | 0.83            |
  | 20   | A Coruña | ES   | 24.62           | 0.39             | 0.81            |

<div class="blog-image">
  <figcaption>Table 1: Top 20 NUTS3 regions in Southwestern Europe by combined heat and elderly exposure (2050, RCP8.5).</figcaption>
</div>

This study is intended for academic purposes only. It has not been peer-reviewed, and no formal uncertainty analysis was performed.

[1] https://climate.copernicus.eu/major-heatwave-southwestern-europe-during-third-warmest-august-record
[2] Thrasher, B., et al. (2012). "Technical Note: Bias correcting climate model simulated daily temperature extremes with quantile mapping," Hydrology and Earth System Sciences, 16(9), 3309-3314
[3] https://doi.org/10.2908/PROJ_19RP3 [28.03.2026]
