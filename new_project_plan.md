


# Research Question
What is the relationship between U.S. foreign aid policy and the U.N. voting attitudes of those recipient nations? Do those recipient nations voting preferences align with those favored by the United States? 


# The Data

## A. United Nations Data 
https://dataverse.harvard.edu/dataset.xhtml?persistentId=hdl:1902.1/12379
Required Citations: 
- Inter-university Consortium for Political and Social Research. United Nations Roll Call Data, 1946-1985. Ann Arbor, MI: Inter-university Consortium for Political and Social Research [distributor], 1992-02-16. https://doi.org/10.3886/ICPSR05512.v1
- Erik Voeten "Data and Analyses of Voting in the UN General Assembly" Routledge Handbook of International Organization, edited by Bob Reinalda (published May 27, 2013). Available at SSRN: http://ssrn.com/abstract=2111149
*Second citation made at the request indicated by author at < >

### Vote Records Data
-  


### Vote Description Data
- rcid: resolution ID, can be used as foreign key to other datasets 
- session: UNGA session date 
- short: short description
- descr: longer description
- important: whether said resolution was deemed "important" by U.S. State Department 

### Issue codes (non-exclusive):
* ME: Votes relating to the Israeli-Palestinian conflict
* NU: Votes relating to nuclear weapons and disarmament/arms control
* CO: Votes relating to colonialism
* HR: Votes relating to human rights
* EC: Votes relating to economic development

## B. Foreign Aid Data 
https://explorer.usaid.gov/about.html

## C. Other Data Sources
Other data sources may be used and/or merged as deemed fit to rigorously probe the stated research question. Potential "other" data sources can include, but not limited to, geographic data, population demographics, data regarding political history of countries/political tilt and potential inherent "bias" against the United States (i.e. Soviet bloc ca. 20th century). 



# Licenses 
1. The UN Voting data is released under a CC0 "Public Domain Dedication" license. It is expected, furthermore, that all data used from Harvard Dataverse and child sites be subject to the following community norms found at https://dataverse.org/best-practices/dataverse-community-norms. 
2. USAID.gov data is released under a "Partner Data License" (https://www.usaid.gov/data/license-data-created-usaid-partners) which "which include the right to reproduce, publish, or otherwise use the data, through a Creative Commons Attribution-No Derivatives 4.0 International License"

# Deliverables 
The plan insofar is to produce the following deliverables: 
1. A visualization similar to that found in https://www.heritage.org/global-politics/report/thirty-years-voting-the-un-general-assembly-the-us-nearly-always-the (Chart 2). 
2. An answer to the research question, both quantitatively and qualitiatively: 
  - Quantitatively: potential measures might include a correlation coefficient, a statistical model of *voting_alignment* vs. *foreign aid* and other covariates, a probabilistic (logistic) model of likelihood of US voting alignment, etc. 
  - Qualitiatively: Via visualization, thorough analysis and textual documentation, etc. 
