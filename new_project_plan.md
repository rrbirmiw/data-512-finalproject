
# Introduction

The linkage between United States foreign aid and United Nations voting alignment has been a longstanding issue. Most recently, the issue has reignited with the Trump Administration in 2018 pledging to severely cut -- punish -- recipient nations of US foreign aid if said countries do not back US-preferred resolutions at the United Nations: 


- "All of these nations that take our money and then they vote against us at the Security Council or they vote against us…at the Assembly…. Well, we’re watching those votes. Let them vote against us; we’ll save a lot.” (President Donald J. Trump. Dec 20, 2017). (https://www.cgdev.org/publication/linking-us-foreign-aid-un-votes-what-are-implications)
- "President Trump and I are pushing to draw a closer connection between US foreign aid and how countries vote at the UN.” – US Ambassador to the UN Nikki Haley. 3/5/2018). https://www.cgdev.org/publication/linking-us-foreign-aid-un-votes-what-are-implications

Yet this quid-pro-quo issue has existed even prior to the current administration's hawkish foreign policy. For example, a research report published in the Heritage Foundation: *Thirty Years of Voting in the U.N. General Assembly: The U.S. Is Nearly Always in the Minority* detail how US Congress has asked for decades concerning the potential *disparity* between aid and voting alignment -- that surprisingly nations with largest US aid have orthogonal voting alignment to US preferences. This publication comes to the conclusion that: "Indeed, over the past 10 UNGA sessions, on average, 81.9 percent of all development assistance recipients (177 countries in all) voted against the U.S. in a majority of the overall non-consensus votes, and 68.9 percent voted against the U.S. in a majority of the important non-consensus votes."
https://www.heritage.org/global-politics/report/thirty-years-voting-the-un-general-assembly-the-us-nearly-always-the

The question, therefore, is what is the true relationship between US foreign aid policy and voting alignment, if a clear pattern even exists. 

# Research Question
What is the relationship between U.S. foreign aid policy and the U.N. voting attitudes of those recipient nations? Do those recipient nations voting preferences align with those favored by the United States? 


# The Data

## A. United Nations Data 
https://dataverse.harvard.edu/dataset.xhtml?persistentId=hdl:1902.1/12379
Required Citations: 
- Inter-university Consortium for Political and Social Research. United Nations Roll Call Data, 1946-1985. Ann Arbor, MI: Inter-university Consortium for Political and Social Research [distributor], 1992-02-16. https://doi.org/10.3886/ICPSR05512.v1
- Erik Voeten "Data and Analyses of Voting in the UN General Assembly" Routledge Handbook of International Organization, edited by Bob Reinalda (published May 27, 2013). Available at SSRN: http://ssrn.com/abstract=2111149
*Second citation made at the request indicated by author at the **Codebook** found at the above link

### Vote Records Data
-  rcid: resolution ID, can be used as foreign key to other datasets 
- vote_type: i.e. yes/no/abstain/etc
- ccode: country code
- session: UNGA (United Nations General Assembly) session number (1-99)

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
Other data sources may be used and/or merged as deemed fit to rigorously probe the stated research question. Potential "other" data sources can include, but not limited to, geographic data, population demographics, data regarding political history of countries/political tilt and potential inherent "bias" against the United States (i.e. Soviet bloc ca. 20th century). See *Human-Centered Considerations below* 



# Licenses 
1. The UN Voting data is released under a CC0 "Public Domain Dedication" license. It is expected, furthermore, that all data used from Harvard Dataverse and child sites be subject to the following community norms found at https://dataverse.org/best-practices/dataverse-community-norms. 
2. USAID.gov data is released under a "Partner Data License" (https://www.usaid.gov/data/license-data-created-usaid-partners) which "which include the right to reproduce, publish, or otherwise use the data, through a Creative Commons Attribution-No Derivatives 4.0 International License"

# Deliverables 
The plan insofar is to produce the following deliverables: 
1. A visualization similar to that found in https://www.heritage.org/global-politics/report/thirty-years-voting-the-un-general-assembly-the-us-nearly-always-the (Chart 2). 
2. An answer to the research question, both quantitatively and qualitiatively: 
  - Quantitatively: potential measures might include a correlation coefficient, a statistical model of *voting_alignment* vs. *foreign aid* and other covariates, a probabilistic (logistic) model of likelihood of US voting alignment, etc. 
  - Qualitiatively: Via visualization, thorough analysis and textual documentation, etc. 
3. Source code used to produce all results and analyses
4. Concerns and considerations/assumptions used in the analysis 

# Human-Centered Considerations

This project asks to seek a qualitative and potentially quantitative relationship between two domains: UN voting records (w.r.t pro-US resolutions) and US foreign aid data. However, seeking such a *A implies B* logic is understandibly short-sighted. There can be a myriad of other factors that influence voting alignment: cultural repression, socioeconomic conditions, historical significance, human suffering, alliances, post-war rebuilding efforts, etc. As a result, any conclusion made by the analysis of this project would result from one "angle"; furthermore that conclusion(s) maybe prone to biases in the data, such as those population and external biases: a vote of yay/nay/abstain can have a much richer and more nuanced reasoning than our quid-pro-quo investigation. Certainly, it is impossible to control for all these external factors in the study, but some efforts can be made. Although not fully determined yet, some ideas include: 
* controlling for NATO/Soviet bloc alliances 
* controlling and clustering by/for GDP and GDP-per-capita (as proxy of socioeconomic health)
* controlling for resolution "type" -- is it dealing with human rights? conflict? (See ISSUE CODES above)
* controlling for time period -- for example voting preferences ca. post-WWII Marshall Plan-era cannot be compared to foreign policy during U.S. policy of containment roughly ~30 years later. Those worldviews are 180. 

# References
1. https://www.heritage.org/global-politics/report/thirty-years-voting-the-un-general-assembly-the-us-nearly-always-the
2. https://www.cgdev.org/publication/linking-us-foreign-aid-un-votes-what-are-implications
3. https://foreignpolicy.com/2018/03/15/haley-vote-with-u-s-at-u-n-or-well-cut-your-aid/
4. https://dataverse.harvard.edu/dataset.xhtml?persistentId=hdl:1902.1/12379
5. Assignment details: https://wiki.communitydata.cc/Human_Centered_Data_Science_(Fall_2018)/Assignments#A4:_Final_project_plan
6. Please see *Codebook* found in this repository, provided by authors of the UN data
