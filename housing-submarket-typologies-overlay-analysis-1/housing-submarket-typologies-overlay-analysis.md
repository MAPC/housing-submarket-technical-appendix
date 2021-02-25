---
description: 'Author: Caitlin Spence'
---

# Housing Submarket Overlays: People, Conditions, and Opportunities

The overlay analysis component of the Housing Submarket Typologies project analyzes the demographic characteristics, available amenities, and lending history of each submarket. The submarket properties explored in the overlay analysis are shown in the table below.

| **Type** | **Potential Variable** | **Spatial Aggregation Unit** | **Aggregation methods** |
| :--- | :--- | :--- | :--- |
| Demographics | Black population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Hispanic Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Asian Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | White population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Foreign Born Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Noncitizen Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Cost Burdened Households \(&gt;50%\) \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Unemployed \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Bachelors or More \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Change in Bachelors or More \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Change in Black Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Change in Hispanic or Latinx Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Change in White Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Change in Asian Population \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Mortgage approval: White rate vs. rate for Black, LatinX, and Native American applicants | Submarket | Mean, median, range |
|  | Limited English language ability \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Households with Children Under 18 \(total, %\) | Tract, Submarket | Mean, median, range, sum |
|  | Percent households with adult over 65 \(total, %\) | Tract, Submarket | Mean, median, range, sum |
| Amenity | Jobs within 45 minutes by transit | Tract, Submarket | Mean, median, range, sum |
|  | Proximity to Public Transit | Submarket | Fraction of submarket area in each station class |
|  | School quality | Tract, Submarket | Mean, median, range, weighted average \(weighted by number of households with kids in each tract\) |
| Policy | Red-lined areas | Submarket | Fraction of submarket area in each HOLC grade |
| Climate & change | Heat exposure | Tract, Submarket | Mean, median, range |
|  | Sea level rise flooding exposure \(8"\) | Tract, Submarket | Mean, median, range |
|  | Sea level rise flooding exposure \(3'4"\) | Tract, Submarket | Mean, median, range |
|  | Floodplain exposure | Tract, Submarket | Mean, median, range |

_Data Sources and Analysis_

Demographic variables are sourced from the U.S. Census American Community Survey \(ACS\) tract-level five-year averages from 2014-2018. With the exception of the change in population with a Bachelor’s decree or higher, changes in demographic characteristics are estimated by comparing the ACS 2014-2018 estimates with U.S. Decennial Census 2000 tract-level data. Changes in population with a Bachelor’s degree or higher were estimated by comparing ACS 2014-2018 data with ACS 2006-2010 data.

Mortgage approval rates by race and ethnicity were estimated from the Home Mortgage Disclosure Act datasets from 2013-2017. The HMDA applicant incomes reported each year prior to 2017 were converted to 2017 U.S. Dollars using an inflation calculator at [https://www.usinflationcalculator.com/](https://www.usinflationcalculator.com/). We calculated the share of applications with combined income greater than $125,000 \(2017 dollars\) per year whose mortgage applications were approved. We calculated this approval rate for two groups: First, applications in which at least one applicant was white; Second, for applications in which at least one applicant was Black, LatinX, or Native American.

Transportation accessibility metrics were determined based on MAPC analysis of existing datasets. First, we estimated the number of jobs accessible within 45 minutes by transit in each tract as the average census block-level transit accessibility estimates produced by the Minnesota Accessibility Observatory \(2016\). We also determined the share of each submarket’s area that lies within one half mile of several classes of transit station. The transit station classes and half-mile station area geometry were sourced from a prior MAPC analysis \(CITATION\).

The analysis incorporated summaries of several Massachusetts Comprehensive Assessment System \(MCAS\) district-level 3rd through 8th grade Math and ELA growth and achievement metrics as indicators of school quality within each submarket. Each tract was assigned to a unique Massachusetts school district so that the district-level MCAS scores could be matched with the tracts most likely to participate in that district. The analysis included MCAS scores from public school districts only and excluded charter school districts. Only districts which included grades 3 through 8 were included in the analysis except in locations where no single district covered grades 3 through 8. Several municipalities in the study area maintain municipal elementary and/or middle school districts and share an upper-grades \(for example, high school\) district with one or more neighboring municipalities. In these areas, MCAS metrics were assigned based on the lower-grades district.

We included 1938 lending risk rating spatial data collected by the Digital Scholarship Lab at the University of Richmond as part of the “Mapping Inequality: Redlining in New Deal America” project. These data did not cover the entire study area, but did include key urban areas. Using the submarket geometry, we calculated the share of each submarket’s total area that exists within each Home Owner’s Loan Corporation \(HOLC\) lending rating class of A \(most desirable, least risk\) through D \(least desirable, high risk\).

Lastly we analyzed the exposure of each submarket to present and future climate hazards using tract-level hazard exposure metrics from a previous MAPC analysis \(REFERENCE\). The dataset contains indicators of exposure to heat islands, riverine and coastal flooding, and storm surge flooding under two future sea level scenarios.

_Summarizing overlays across submarkets_

We summarize each overlay variable in one of two ways. The first way relies on a tract-level distribution of overlay variable values within each submarket and reports the mean, median, and other statistics of the tracts’ overlay values within each submarket. The second way summarizes the overlay metric at the submarket level directly without creating tract-level estimates of the overlay metric as an intermediate step.

We present summaries of tract-level overlay metrics within each summary as tables and in violin plots. Violin plots are an augmented version of a box plot. They display the distribution of datapoints as a median point, interquartile range box or bar, and thin line indicating the range of the dataset excluding outliers. A curved shape imposed behind this boxplot displays a smoothed kernel density estimate of the data’s distribution. Violin plots are useful when comparing distributions of groups of data, especially when the distributions may have nonstandard properties such as multiple modes, asymmetry, or fat tails.

We report submarket-level overlay metrics as tables and bar charts.

