# Final Project
*Template for this README comes from https://github.com/Ironholds/data-512-a2* 

Name: Rahul Birmiwal 

Date: 12/9/18

The assignment comes from Jonathan T. Morgan, Os Keyes. University of Washington. DATA 512: Human-Centered Data Science. Autumn Quarter 2018. Whose description comes from https://wiki.communitydata.cc/Human_Centered_Data_Science_(Fall_2018)/Assignments#A6:_Final_project_report

## Goal and Research Question
This project seeks to use human-centered data science methods, exploratory data analysis armed with an "interpretivist" mindset, to find relationship(s) between US foreign aid dispersment and increased pro-US alignment in voting behavior in the United States General Assmebly. Furthermore, we seek to determine if a causal relationship exists: does an "impulse" of foreign aid induce increased alignment in the near term by the recipient nation of that aid influx? 

## Results

The project and analysis dives through various structural models of the above research quesiton. After conditioning on income and geographic region as a "best-suitable" proxy for the infinite possibilities of socio-geopolitical-historical-ethnographic externalities/hidden biases in the relationships between foreign aid and alignment (i.e. the wars in Afghanistan and Iraq are intrinsically correlated with mountains of aid)...we see that aid does induce alignment. 

## Data sources used

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

-Title: Foreign Aid Explorer: The official record of U.S. foreign aid
-Author: U.S. Agency for International Development (USAID)

US foreign aid data comes from the US Department for Foreign Aid @ USAID.gov. https://explorer.usaid.gov/about.html#tab-about. The data set lists all individual foreign aid transactions 1946-2017. The data can be downloaded from: https://explorer.usaid.gov/data.html under "complete dataset." 

Columns of interest in this dataset's schema are: 
- income_group_name: To which income-group the US Foreign Aid/State Department offices classify that country 
- region_group: Likewise for geographic region 
- constant_amount: Amount in constant (inflation-adjusted) US dollars of the aid in that transaction to that country 

## Licenses 
- The UN Voting data is released under a CC0 "Public Domain Dedication" license. It is expected, furthermore, that all data used from Harvard Dataverse and child sites be subject to the following community norms found at https://dataverse.org/best-practices/dataverse-community-norms.
- USAID.gov data is released under a "Partner Data License" (https://www.usaid.gov/data/license-data-created-usaid-partners) which "which include the right to reproduce, publish, or otherwise use the data, through a Creative Commons Attribution-No Derivatives 4.0 International License"
- This project is released under an MIT License 

## Resources used
This analysis was prepared using Python 3.5 running in a Jupyter Notebook environment.  
Documentation for Python can be found here: https://docs.python.org/3.5/  
Documentation for Jupyter Notebook can be found here: http://jupyter-notebook.readthedocs.io/en/latest/  

## Dependencies: 
Following Python library dependencies are required to run the notebook: 
- numpy: https://docs.scipy.org/doc/numpy-1.15.1/reference/
- pandas: https://pandas.pydata.org
- scikit-learn: http://scikit-learn.org/stable/
- seaborn (for visualization): https://seaborn.pydata.org
- scipy: https://www.scipy.org
Please ensure all dependencies installed in the working environment before running the notebook. 

## Files Created
A jupyter notebook `data512-finalproject.ipynb`             

## Code

Code and Python project contained in the jupyter notebook `data512-finalproject.ipynb`      

## Visualizations Created
Various visualizations are used in the Jupyter notebook along the way as part of the exploratory data analysis 
 
