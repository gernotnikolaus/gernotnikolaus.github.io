---
layout: default
title: "Projected Heat Exposure for Elderly Populations in Southwestern Europe under Future Climate Scenarios"
date: 2026-03-29
categories: [projects]
permalink: /projects/ProjectedHeatExposureElderlyPopulationsSouthwesternEurope
---

# Projected Heat Exposure for Elderly Populations in Southwestern Europe under Future Climate Scenarios (RCP4.5 and RCP8.5)

August 2025 was the third-warmest August on record globally; Heatwaves are becoming increasingly frequent and intense in Southwestern Europe*. Using NASA/NEX-GDDP climate models (MIROC5, GFDL-CM3, HadGEM2-ES), EUROSTAT demographic projections, I analyzed the future exposure for elderly populations in Portugal, Spain, and France to summer heat under different climate scenarios (current, RCP4.5, and RCP8.5).

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

While the elderly share 2025 is quite even in the countries, Spain will have an increasing elderly grow in northwestern and inland regions by 2050 (Figure 4). Regions such as Zamora, León, and Asturias are projected to see elderly shares rise to 43–47%. Portugal shows moderate increases in elderly share, while France remains comparatively stable (Table 1).

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

This study is intended for academic purposes only. It has not been peer-reviewed, and no formal uncertainty analysis was performed.

* https://climate.copernicus.eu/major-heatwave-southwestern-europe-during-third-warmest-august-record
