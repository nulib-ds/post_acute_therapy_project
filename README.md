# A Quick Introduction to Exploring the Maps

### Using Widgets
https://github.com/user-attachments/assets/5079460e-9c8a-4d38-9be2-1c4dc3b2f3e8


### Navigating the Layer List
https://github.com/user-attachments/assets/2ecae4c2-719f-49f2-ae3a-2bfb354b3162


### Exporting Data
https://github.com/user-attachments/assets/d8e54412-daa9-4402-9f42-a7f6fb226d27



# Technical Map Usage Instructions

### 1.1 Utilization Rates maps:

On the left-side bar, click the box for this type of map. Then, use the arrow (“>”) to expand on the sub-options and select the facility type: SNFs, HHAs, IRFs or SNFs+HHAs+IRFs. When you select a facility, then you need to again use the arrow to expand on the sub-option and select your time frame of choice: 2022 (most recent year available when the maps were developed), 2019 (pre-COVID 19 and prior payment and documentation reforms for HHAs and SNFs), 2013 (oldest data available), or yearly average for ten years combined [2013-2022]. A color-gradient map (choropleth map) will then emerge with the data selection you have activated.
A legend emerges at the right side of the screen; it includes the legend of utilization rates both in minutes per beneficiary and in percentile ranks nationwide. You can also use the zoom option on the right side of the screen. Finally, you can click on specific counties and a pop-up window will show the county-level data for that given year.  

### 1.2 Hot Spot Analysis Maps:
In the same left-side bar, first select this type of map (i.e., click its box), then whether you want to select the General HSA or Emergent HAS – as options that pop up underneath, with the use of the arrow. 
The “General HAS” implies that you select first the facility type, and then the year underneath it. Only with all these options activated does the map emerge. The “Emergent HSA” only implies selecting the facility type in addition to this type of analysis.

### 1.3 State-level Rural Client Utilization Maps:
In the same left-side bar, first select this type of map (i.e., click its box). Then, expand on (using the arrow) to observe the sub-options available, and then select the facility type you want.

### 1.4 Provider Facilities / Rural & Medically Underserved Counties / State and US Division Boundaries:
For these options, which can be overlayed with the mapped utilization data, the selections are simpler. There are no year selections to be made for any of the above.
Facility selections only apply to “Provider Facilities”. You can activate the four options at the same time for these, if you want. For the “Rural & Medically Underserved Counties”, we recommend selecting just one option, as they are alternative to one another and hard to visualize when more than one is activated at the same time.


# Methods details, including limitations of the data source


### 2.1.	How the utilization rates were computed over its data source:
We computed county-level, risk-adjusted rehabilitation therapy utilization rates. That includes the county-level total yearly minutes provided by physical therapy, occupational therapy, and speech and language pathology, which were here summed up. The Medicare Post-Acute Care and Hospice Provider Utilization and Payment Public Use File (PAC PUF), released in 2024 with data up to 2022, was the data source for the yearly therapy minutes.1 While this file contains data at the provider level, the therapy minutes were summed at the county level. County-level, total therapy minutes were first computed for each PAC site (i.e., SNF, HHA, IRF). Then, we did it for HHAs, SNFs and IRFs together. Therapy minutes per site were then transformed into per-capita utilization: i.e. divided by the of each county’s yearly number of Medicare fee-for-service (FFS) beneficiaries. The latter was obtained through the Medicare Geographic Variation Public Use File (GV PUF).2 Finally, we risk-adjusted the per-capita utilization to the county-level risk of healthcare utilization. For that, we used county-level average score of the Hierarchical Condition Category – a combined indicator of higher/lower population utilization risk, used for determining capitated payments for Medicare Advantage programs.2 3 This indicator was also extracted from the GV PUF.2 

### 2.2.	Missing values and data transformation for computing utilization rates: 
We used data from 2013 to 2022, which involved handling some missing values or transforming some of the data. For instance, there are no IRF therapy-utilization values from 2013 to 2015, replaced with a 2% retrospective decrease per year since 2016 (i.e., average yearly change from 2016 onwards). Furthermore, public-domain Medicare data suppressed the therapy minutes for providers that served 10 clients or less per year, here transformed into zeros across the rural-urban gradient. This affected a minority of providers and is not disproportionally rural. For instance, in 2022, only 0.05% of the PAC providers had values suppressed for the three therapies; 17% of those were based in small rural/remote counties, 15% in larger rural counties, and 68% in urban/suburban areas.4 Finally, preliminary visualization revealed that per-capita therapy utilization data of 2021 for SNFs and HHAs followed a unique pattern relative in the years before and year thereafter, as a result of the COVID-19 pandemic, which affected rural areas the most.5-7 To remove the effect of this special event, we replaced the entire 2021 year of county-level SNF and HHA data by the respective average values between 2020 and 2022.  Finally, for the covariates, we frequently had yearly values for some (e.g., 2015-2020) but not for all years; hence, we used the data from the closest year (e.g. the values of 2015 for the preceding years and those of 2020 for the years thereafter).  

### 2.3 How State-Level data was computed
We computed the county-level rural-client utilization percentage, also based on PAC PUF.1 That file contains the percentage of FFS beneficiaries served by each provider that have a rural residency according to the CBSA (i.e., neither metropolitan nor micropolitan in that classification). That file also contains the total number of FFS served by each provider.1 Dividing the former by the latter, we have obtained the total number of rural FFS beneficiaries served by each provider. That number was summed up at the county level, and also transformed into a county-level utilization rate: i.e., divided by each county’s number of FFS Medicare beneficiaries. 
Then, both county-level “total” and “rural-client” utilization rates were risk-adjusted for the county’s Hierarchical Condition Category score of the respective year.2 That indicator has been used, for example, for determining capitated payments for Medicare Advantage programs.2 3 
Subsequently, we summed all county-level risk-adjusted “total” and “rural-client” utilization rates at the State level. This was done to partly overcome data limitations, as we could not allocate rural client utilization to which specific rural county. So, assuming that most cross-county healthcare delivery occurred within a State, we summed the all county-level risk-adjusted utilization rates within each State, both the “total” and “rural-client” one. Finally, at the state-level, we divided the latter by the formed to obtain the state-level, risk-adjusted percentage of rural-client utilization for FFS Medicate beneficiaries, for each year (2013-2022).
The state-level rural utilization percentage (i.e., from now on called actual utilization rate – dependent variable) was compared to an expected utilization percentage. That expected utilization was computed as follows. We used the yearly county-level number of FFS beneficiaries,2 assigned to be rural or urban based the CBSA. Then, we computed the state-level total number of FFS beneficiaries (urban and rural) and the rural alone, dividing the latter for the former to obtain the yearly, state-level percent of FFS beneficiaries that have rural residency. Finally, to obtain the mapped value, we divided the actual state-level rural utilization percentage by the expected one. A result of “1” (i.e., 100% after percent transformation) would reflect rural-urban parity in utilization; any percent value below 100% would reflect the percent magnitude of the rural gap. 

### 2.3.	How the rates were analyzed and displayed
For the hot spot analyses, conducted in ArcGIS Pro software, we a priori log-transformed dependent variables to reduce the impact of yearly outliers,4 which in turn would interfere with this analysis. Finally, we did not include Hawaii and Alaska in the hot spot analyses because of the geographical distances which would also affect the results of the analysis.
The interactive display of the data in the maps, including variable and metrics selection, scaling, display features, supportive and navigation information, among others, were codesigned with a multi-stakeholder advisory board of potential end-users. This advisory group, separated into small groups, met with the principal investigators in two different time points. First, a meeting occurred when initial maps were just being drafted, providing key directions and feedback for the map design definitions. Second, after a complete interactive map website was available, a final meeting occurred to help evaluate, fine tune, set up a dissemination plan, and envision further developments for these maps. The final meeting occurred after an individual beta testing of the maps, released by the investigators. This consultation was deemed “exempt” by the Institutional Review Board of The Ohio State University and all the advisory board members provided written consent for the names and positions to be mentioned.

Name                | Postion                                                               | Affiliation                                                                                                    | Stakeholder background for the role
---                 | ---                                                                   | ---                                                                                                            | --- 
Bogenrief, Jennifer | Director, Regulatory Affairs                                          | American Occupational Therapy Association                                                                      | Rehabilitation professions' policy advocate: Legal and Regulatory Affairs related to the Medicare programs
Ellis, Elissa       | Deputy Director                                                       | APRIL: Association of Programs for Rural Independent Living                                                    | Disability advocate / consumer representative; Rural community-supports advocate
Greiman, Lillie     | Project Director                                                      | RTC: Rural at The Rural Institute for Inclusive Communities; The University of Montana                         | Geographic mapping; rural disability
Jones, Mackenzie    | Health Education Specialist                                           | Montana Disability & Health Program	State-level Public Health Agent                                            | Disability Health Policy and Programing
Lewis, Marquita     | Assistant Professor	                                                  | Medical Social Sciences, Northwestern University                                                               | Community-engaged and health services researcher on rural disparities
Morrow, Corey       | Assistant Professor                                                   | Department of Rehabilitation Sciences, Medical University of South Carolina, Charleston, South Carolina	       | Rural Rehabilitation Researcher
O'Neil, Flannery    | Chief Operating Officer (formerly)                                    | Stroke Onward (formerly)                                                                                       | Disability Advocate / Consumer Representative; Person who experienced a disability; Public health and policy advocate
Potts, Diane        | President                                                             | Illinois Rural Health Association                                                                              | State-level Public Health Agent; Rural Health Advocate
Stringer, Beverly   | Southeast Ohio Community Engagement Manager                           | The Ohio State University and Appalachian Translational Research Network                                       | Regional Engagement and Development; Appalachian Advocate

Table 1: Stakeholder participants in the advisory group for codesigning the interactive map displays, order alphabetically. Positions and affiliations at the time of the engagement.


### 2.4	How the PAC PUF data is collected and the limitations of this data source
Although the PAC PUF has a wealth of utilization information that can be useful and comparable across US geographies, it is important to provide some notes about how the data is collected for dataset, including its limitations. It is also worth noting that the file only entails Part A Medicare fee-for-service data.
#### 2.4.1	Overview of the PAC PUF limitations
We enumerate key PAC PUF limitations here, including the differences in how data were collected across facilitation time and over time. Also, it is important to note the therapy minutes are not exhaustive relative to those indeed delivered, but rather registered according to the prevailing documentation requirements at the given time. Overall, caution should be taken especially on comparisons made over time (especially before 2019 and thereafter for SNFs) and across provider types. Yet, relative or mapped comparisons across geographies (e.g. rural and urban) are more plausible as the documentation requirements were the same for a given time across the USA. How the data is collected by provider type and any inherent limitations are detailed below. 
#### 2.4.2 Data collection for IRFs and its limitations 
The PAC PUF calculates the volume (i.e., minutes) of therapy services by discipline type delivered in IRFs from the IRF Patient Assessment Instrument (IRF-PAI). Completion of the IRF-PAI is required for each Medicare FFS patient discharged from an IRF. Questions O0401 and O0402 report the total minutes of therapy delivered by discipline type during the first two weeks of care. While two weeks roughly equates to an average length of stay, the therapy minutes patients delivered after the initial two weeks (for patients that had a longer than two-weeks stay) were not registered, hence not counted across all the IRFS nationwide and over time.
For the 2015 PAC PUFs or before, there is missing data for volume of therapy services delivered for IRF, as these variables were not active in the IRF-PAI assessment until October 1, 2015. This was noted in the missing values section here, including how we estimated those values.
#### 2.4.3 Data collection for SNFs and its limitations
The PAC PUF calculates the volume (i.e., minutes) of therapy services by discipline type delivered in SNFs from the Long-Term Care Minimum Data Set 3.0 (MDS). For 2019 or before, MDS Part A assessment question O0400 was used to calculate the volume of therapy services delivered. The response to this question only reports therapy minutes performed in the seven days prior to the assessment. For FY 2020 and forward, MDS Part A discharge assessment question O0425 reports the total minutes of therapy delivered by discipline type and is used to calculate the volume of therapy services delivered in the PAC PUF. Consequently, the total number of therapy minutes performed during the SNF stay is not available to report for 2019 or before. For FYs 2020-2022, there is an MDS assessment variable (O0425) available that does report therapy minutes performed for the entire stay covered by Medicare’s Part A SNF benefit. However, this variable is only reported on MDS Part A Discharge assessments, and CMS does not always require a discharge assessment to be completed. Overall, a 13.6% increase in the total number of therapy minutes registered for SNF from 2019 to 2020 was observed, occurring across urban and rural providers, which likely results from this documentation change than actually from an increase in therapy hours delivered.
Longitudinal comparisons for SNFs-based therapy minutes based on the PAC PUF, especially before and after 2019, are affected by documentation changes. However, cross-geographical relative comparisons over time may be less prone to bias as the documentation requirements and changes were applied to all geographic areas and at the same time.

### 2.5	Data collection for HHAs 
Services for HH were obtained from the revenue center files on the Chronic Conditions Data Warehouse and include the following revenue center codes: 0420-0429 (physical therapy), 0430-0439 (occupational therapy), 0440-0449 (speech language pathology). There were no reported changes on how these data are collected, computed or reported over time.

### 2.6. Provider Facilities
The provider facilities are those SNFs, HHAs, and IRFs that, in 2024, were identified by the CMS as being Medicare-certified, whose files and data were obtained from: https://data.cms.gov/provider-data/search. For the HHAs, we only mapped those who had a record, in those files, of offering any of three rehabilitation therapies analyzed here. The mapped data exclusively reflects the extracted information, including any errors in it, and cannot be understood as a form of endorsement, recommendation, or insurances accepted.

 
# References

1. Centers for Medicare & Medicaid Services. Medicare Post-Acute Care and Hospice - by Geography & Provider  [Available from: https://data.cms.gov/provider-summary-by-type-of-service/medicare-post-acute-care-and-hospice-by-geography-provider accessed December 20, 2022.
2. Centers for Medicare & Medicaid Services. Medicare Geographic Variation - by National, State & County  [Available from: https://data.cms.gov/summary-statistics-on-use-and-payments/medicare-geographic-comparisons/medicare-geographic-variation-by-national-state-county.
3. Mroz T. GL, Wong J., et. al. Variation in Use of Home Health Care among Fee-for-Service Medicare Beneficiaries by Rural-Urban Status and Geographic Region: Assessing the Potential for Unmet Need. . Policy Brief #169 2020 WWAMI Rural Health Research Center, University of Washington Seattle, WA 2020
4. Jesus TS, Monteiro PC, Pinho CS, et al. Rural-urban disparities in the utilization of rehabilitation therapies among fee-for-service Medicare beneficiaries: cross-sectional analyses and rural classifications comparison. Uner submission 2025
5. Prusynski RA, Humbert A, Leland NE, et al. Dual impacts of Medicare payment reform and the COVID-19 pandemic on therapy staffing in skilled nursing facilities. Journal of the American Geriatrics Society 2022;Online ahead of print doi: 10.1111/jgs.18208 [published Online First: 2022/12/27]
6. McGarry BE, Grabowski DC, Barnett ML. Severe Staffing And Personal Protective Equipment Shortages Faced By Nursing Homes During The COVID-19 Pandemic. Health Aff (Millwood) 2020;39(10):1812-21. doi: 10.1377/hlthaff.2020.01269 [published Online First: 20200820]
7. Konetzka RT, White EM, Pralea A, et al. A systematic review of long-term care facility characteristics associated with COVID-19 outcomes. J Am Geriatr Soc 2021;69(10):2766-77. doi: 10.1111/jgs.17434 [published Online First: 20210921]





# Work conducted at:

![The Ohio State University](img/ohio_state.png) ![Northwestern Medicine](img/northwestern_medicine.png) ![Northwestern University Libraries](img/NUL_library.png)
 

### Principal Investigator: Tiago Jesus, PhD, OTD, OTR/L,

Division of Occupational Therapy, School of Health and Rehabilitation Sciences, The Ohio State University Wexner Medical Center, Columbus, Ohio, USA. tiago.jesus@osumc.edu

 

### Map design and application: Mech Frazier, MA

GIS Specialist, Digital Scholarship, Northwestern University Libraries, Evanston, Illinois, USA. mech.frazier@northwestern.edu 

 

## Funding:

![NIDILRR](img/NIDILRR.png) ![ACL](img/ACL.png)

Work funded by the Switzer Fellowship, Award #: 90SFGE0046-01-00 from the National Institute on Disability, Independent Living, and Rehabilitation Research (NIDILRR), which is part of the Administration for Community Living (ACL).

Disclaimer: This project supported by the Administration for Community Living (ACL), U.S. Department of Health and Human Services (HHS). The contents are those of the author(s) and do not necessarily represent the official views of, nor an endorsement, by ACL/HHS, or the Administration For Community Living U.S. Government.
