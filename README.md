---
description: >-
  Authors: Seleeke Flingai, Taylor Perez, Sarah Philbrick, Jessie Partridge
  Guerrero, Tim Reardon
---

# MAPC Housing Submarket Typology Analysis

### **Introduction**

Urban and regional planners, policymakers, housing and community development advocates, and more depend on community knowledge and data to plan and implement development strategies, revitalization programs, and other neighborhood-centric policies and interventions. However, neighborhoods selected for such efforts may be targeted in isolation or alongside neighboring communities under the assumption that spatially clustered neighborhoods may experience parallel, intended policy effects. In reality, similar neighborhoods, sharing common challenges and opportunities, may exist throughout the region in a spatially heterogeneous manner, while nearby neighborhoods may actually have vastly different characteristics that could result in unintended policy impacts.

One approach to categorizing neighborhoods that could account for these issues is housing submarket segmentation. Housing submarkets are distinct market segments based on similarities in housing market demographics, socioeconomic data, housing characteristics, and more. An analysis of housing submarkets in our region will be valuable in several ways. A submarket framework can better facilitate the development of policy responses and community development strategies that are tailored to specific submarkets facing unique challenges and opportunities. Additionally, such an analysis can give rise to targeted research that is more relevant to a given submarket or set of submarkets, such as mapping populations vulnerable to residential displacement.

The overall goal of this study was to develop a regional housing submarket typology for Greater Boston. To accomplish this goal, we produced a novel dataset incorporating building stock, housing market, and neighborhood environment information from the U.S. Census Bureau, the Warren Group real estate and mortgage database, and the U.S. Department of Housing and Urban Development. We then compared two well-studied clustering techniques – latent profile analysis \(LPA\) and _k_-medoids – in order to cluster census tracts throughout the region into housing submarket types. Ultimately, we identified seven housing submarkets that are distinct enough from one another to signify significant differences in micro-level housing market characteristics. Our findings provide a valuable tool that planners, policymakers, researchers, and others can use to develop appropriate, targeted programs, policies, and research efforts for the range of neighborhood types that may exist within a given municipality or across the region.

### Study area and data

The data for this study were drawn from four sources: the U.S. Census Bureau’s American Community Survey \(ACS\) 5-year estimates from 2013-2017, the 2000 U.S. Decennial Census, the Warren Group real estate and mortgage database, and the U.S. Department of Housing and Urban Development \(HUD\). Data were collected for the 706 census tracts within the 101 municipalities comprising the MAPC region and standardized to 2010 census tract boundaries using Brown University’s Longitudinal Tract Data Base \(LTDB\). After removing census tracts with missing data, no population, or zero housing units, 681 census tracts remained and were included in the final analyses.

Housing market demographics, contract rent, and housing density were collected from both the 2000 US Decennial Census and ACS 2013-2017 5-year sample estimates; these variables were used to describe current conditions \(ACS data\) or a change in conditions from the year 2000. Household income, vacancy rates, and housing characteristics \(e.g., housing stock age\) were drawn from ACS 2013-2017 data. The share of subsidized housing units in a given tract were calculated using data from HUD. Median home value and housing sales characteristics \(e.g., the percent of residential sales purchased by a business\) were drawn from property data collected by The Warren Group, a New England-based real estate and mortgage data tracking company. 

