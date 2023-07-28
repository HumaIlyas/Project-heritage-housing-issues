# Heritage Housing Issues

## [View live website](https://heritage-house-prices-80a4732eae28.herokuapp.com/)

---
## Table of Contents
- [Heritage Housing Issues](#heritage-housing-issues)
  - [View live website](#view-live-website)
  - [Table of Contents](#table-of-contents)
  - [Dataset Content](#dataset-content)
  - [Business Requirements](#business-requirements)
  - [Hypothesis and Validation Methods](#hypothesis-and-validation-methods)
  - [The rationale to map the business requirements to the Data Visualisations and ML tasks](#the-rationale-to-map-the-business-requirements-to-the-data-visualisations-and-ml-tasks)
  - [ML Business Case](#ml-business-case)
  - [Dashboard Design](#dashboard-design)
- [Issues Found During App Development and Deployment](#issues-found-during-app-development-and-deployment)
- [Unfixed Bugs](#unfixed-bugs)
- [Deployment](#deployment)
  - [GitHub](#github)
  - [Heroku](#heroku)
  - [View live website](#view-live-website-1)
- [Technologies Used](#technologies-used)
    - [GitHub](#github-1)
    - [Git](#git)
    - [Codeanywhere](#codeanywhere)
    - [Heroku](#heroku-1)
    - [Python](#python)
  - [Main Data Analysis and Machine Learning Libraries](#main-data-analysis-and-machine-learning-libraries)
- [Credits](#credits)
  - [Acknowledgements](#acknowledgements)


---
## Dataset Content
* The dataset is sourced from [Kaggle](https://www.kaggle.com/codeinstitute/housing-prices-data). We then created a fictitious user story where predictive analytics can be applied in a real project in the workplace. 
* The dataset has almost 1.5 thousand rows and represents housing records from Ames, Iowa, indicating house profile (Floor Area, Basement, Garage, Kitchen, Lot, Porch, Wood Deck, Year Built) and its respective sale price for houses built between 1872 and 2010.

|Variable|Meaning|Units|
|:----|:----|:----|
|1stFlrSF|First Floor square feet|334 - 4692|
|2ndFlrSF|Second-floor square feet|0 - 2065|
|BedroomAbvGr|Bedrooms above grade (does NOT include basement bedrooms)|0 - 8|
|BsmtExposure|Refers to walkout or garden level walls|Gd: Good Exposure; Av: Average Exposure; Mn: Minimum Exposure; No: No Exposure; None: No Basement|
|BsmtFinType1|Rating of basement finished area|GLQ: Good Living Quarters; ALQ: Average Living Quarters; BLQ: Below Average Living Quarters; Rec: Average Rec Room; LwQ: Low Quality; Unf: Unfinshed; None: No Basement|
|BsmtFinSF1|Type 1 finished square feet|0 - 5644|
|BsmtUnfSF|Unfinished square feet of basement area|0 - 2336|
|TotalBsmtSF|Total square feet of basement area|0 - 6110|
|GarageArea|Size of garage in square feet|0 - 1418|
|GarageFinish|Interior finish of the garage|Fin: Finished; RFn: Rough Finished; Unf: Unfinished; None: No Garage|
|GarageYrBlt|Year garage was built|1900 - 2010|
|GrLivArea|Above grade (ground) living area square feet|334 - 5642|
|KitchenQual|Kitchen quality|Ex: Excellent; Gd: Good; TA: Typical/Average; Fa: Fair; Po: Poor|
|LotArea| Lot size in square feet|1300 - 215245|
|LotFrontage| Linear feet of street connected to property|21 - 313|
|MasVnrArea|Masonry veneer area in square feet|0 - 1600|
|EnclosedPorch|Enclosed porch area in square feet|0 - 286|
|OpenPorchSF|Open porch area in square feet|0 - 547|
|OverallCond|Rates the overall condition of the house|10: Very Excellent; 9: Excellent; 8: Very Good; 7: Good; 6: Above Average; 5: Average; 4: Below Average; 3: Fair; 2: Poor; 1: Very Poor|
|OverallQual|Rates the overall material and finish of the house|10: Very Excellent; 9: Excellent; 8: Very Good; 7: Good; 6: Above Average; 5: Average; 4: Below Average; 3: Fair; 2: Poor; 1: Very Poor|
|WoodDeckSF|Wood deck area in square feet|0 - 736|
|YearBuilt|Original construction date|1872 - 2010|
|YearRemodAdd|Remodel date (same as construction date if no remodelling or additions)|1950 - 2010|
|SalePrice|Sale Price|34900 - 755000|

## Business Requirements
As a good friend, you are requested by your friend, who has received an inheritance from a deceased great-grandfather located in Ames, Iowa, to help in maximizing the sales price for the inherited properties.

Although your friend has an excellent understanding of property prices in her own state and residential area, she fears that basing her estimates for property worth on her current knowledge might lead to inaccurate appraisals. What makes a house desirable and valuable where she comes from might not be the same in Ames, Iowa. She found a public dataset with house prices for Ames, Iowa, and will provide you with that

* 1 - The client is interested in discovering how the house attributes correlate with the sale price. Therefore, the client expects data visualizations of the correlated variables against the sale price to show that.
* 2 - The client is interested to predict the house sales price from her 4 inherited houses, and any other house in Ames, Iowa.


## Hypothesis and Validation Methods
* We suspect that the distribution of the sale prices is skewed to the right which might lead to a problem when it comes to predicting high sale prices. To validate the project hypothesis about the shape of the distribution, we plot a combined boxplot/histogram of the sale price.


## The rationale to map the business requirements to the Data Visualisations and ML tasks

* Business requirement 1: Correlation study and data visualization
  * As a client I want to inspect the house records data so that I can get an idea of which variables are important for the sale price.
  * As a client I want to display a heatmap of the spearman correlation coefficients so that I can order the variables by importance concerning the sale price.
  * As a client I want to plot the important variables against the sale price so that I can visualize how such a variable is correlated with the sale price.
* Business requirement 2:
  * As a client I want to display the inherited houses records data so that I can easily find a house attribute.
  * As a client I want to use an ML model so that I can predict the price of my four inherited houses in Ames, Iowa.
  * As a client I want to use the ML model so that I can predict the price of any other house in Ames, Iowa.

## ML Business Case
1. What are the business requirements?
   * The client is interested in discovering how house attributes correlate with sale prices. Therefore, the client expects data visualizations of the correlated variables against the sale price.
   * The client is interested in predicting the house sale prices from her 4 inherited houses, and any other house in Ames, Iowa.
2. Is there any business requirement that can be answered with conventional data analysis?
   * Yes, we can use conventional data analysis to investigate how house attributes are correlated with the sale prices.
3. Does the client need a dashboard or an API endpoint?
   * The client needs a dashboard
4. What does the client consider as a successful project outcome?
   * A study showing the most relevant variables correlated to sale price.
   * Also, a capability to predict the sale price for the 4 inherited houses, as well as any other house in Ames, Iowa.
5. Can you break down the project into Epics and User Stories?
   * Information gathering and data collection.
   * Data visualization, cleaning, and preparation.
   * Model training, optimization and validation.
   * Dashboard planning, designing, and development.
   * Dashboard deployment and release.
6. Ethical or Privacy concerns?
   * No. The client found a public dataset.
7. Does the data suggest a particular model?
   * The data suggests a regressor where the target is the sale price.
8. What are the model's inputs and intended outputs?
   * The inputs are house attribute information and the output is the predicted sale price.
9. What are the criteria for the performance goal of the predictions?
   * We agreed with the client on an R2 score of at least 0.75 on the train set as well as on the test set.
10. How will the client benefit?
    * The client will maximize the sales price for the inherited properties.

## Dashboard Design
The dashboard consists of five pages:

1. The first page describes the project dataset and states the business requiremnents.
2. The second page fullfills the first project requirement. It starts with stating the requirement in an info box. Three checkboxes implement the user stories relating to the first project requirement (see Business Requirements). When checked they display:
   * A table showing the dataset.
   * A heatmap of Spearman correlation coefficients.
   * Scatterplots of correlated variables against sell price. The page also has a description of the meaning of the variables and a general conclusion.
3. The third page fullfills the second project requirement (see Business Requirements). It has two tables showing the client's inherited houses data and predicted sale prices respectively. The sum of the sale prices is also displayed. The second part of the page has two input widgets and a button that enables the user to predict the sale price based on the inputs.
4. The fourth page states the project hypothesis and its validation. It shows the distribution of sale price. Finally there is a paragraph about the model's limitation and how it may be connected to the project hypothesis.
5. The fifth page starts with a general conclusion about the performance of the ML model. The pipeline steps are then presented followed by a bar plot showing the importance of each feature in the train set. The remaining two parts evaluate the ML model by computing the R2 score and three different error measures and by displaying a scatterplot of predicted versus actual sale price (which is the target).

---
# Issues Found During App Development and Deployment
The following issues were found during app development and deployment<br>
- To deploy Heritage Housing Issues on Heroku, the stack by default did not support the Python version used to develop the app.<br>
I adjusted this issue:
   * By changing the stack of my project from 22 to 2

---
# Unfixed Bugs

* There is no unfixed bugs.
---
# Deployment
- Heritage Housing Issues was deployed using Code Institute's mock terminal for Heroku.

## GitHub
Codeanywhere was used as a development environment where all the changes were committed to git version control system. The push command was used in Codeanywhere to save changes into GitHub.

## Heroku
**The steps for deployment are as follows:**
1. Fork or clone this repository
2. Log in to Heroku and create an App
3. At the Deploy tab, select GitHub as the deployment method
4. Link the Heroku app to the Github repository [Project-5](https://github.com/HumaIlyas/Project-heritage-housing-issues)
5. Select the branch to be deployed, then click Deploy Branch.
6. The deployment process should happen smoothly if all deployment files are fully functional
7. When the message appeared "Your app was successfully deployed"
8. Click on "View" to open the app

**In case of need to change to stack-20 in Heroku will be done by:**
1. In Heroku click on Account Settings (under the avatar menu) on the Heroku Dashboard.
2. Scroll down to the API Key section and click Reveal. Copy the key.
3. Back in your IDE workspace, enter the following command in the terminal: heroku login -i , and enter your email then API key that you copied when prompted.
4. Then use the command heroku stack:set heroku-20 -a <the_name_of_your_app>
5. Now deploy again in the Heroku app

## [View live website](https://heritage-house-prices-80a4732eae28.herokuapp.com/)

---
# Technologies Used
Different technologies were used to complete the contents of Heritage Housing Issues.

### GitHub
* As a software hosting platform to keep project in a remote location.

### Git
* As a version-control system tracking.

### Codeanywhere
* As a development hosting platform.

### Heroku
* Platform as a service offering to carry out application deployment, scaling, and management.

### Python
*  As an interpreted, interactive, and object oriented scripting language.

---
## Main Data Analysis and Machine Learning Libraries
The libraries used in this project are:

* numpy==1.19.1
* pandas==1.1.2
* matplotlib==3.3.1
* seaborn==0.11.0
* pandas-profiling==3.2.0
* streamlit==1.10.0
* feature-engine==1.0.2
* scikit-learn==0.24.2
**As an example,** Seaborn was used to creating the heatmap of correlation coefficients, pandas-profiling to explore the variables in the dataset by showing their distribution, how many missing data they contain etc.

---
# Credits 
To complete the contents of Heritage Housing Issues, I learned coding and collected the information from different sources.

* Learned Python coding from [Code Institute](https://learn.codeinstitute.net/)
- Used Code Institute student template [template](https://github.com/Code-Institute-Solutions/milestone-project-heritage-housing-issues)
* Collected information on good and bad coding practices from:
  * [Documenting Python Code](https://realpython.com/documenting-python-code/)

- The description on the prediction if a prospect will churn provided by the tutor of the Code Institute with [Predict Churn](https://github.com/Code-Institute-Solutions/churnometer) and an app [Churnometer](https://churnometer.herokuapp.com/) was useful as well as an inspiration to work on the project [Heritage Housing Issues](https://github.com/HumaIlyas/Project-heritage-housing-issues) and design an app [House Prices in Ames, Iowa](https://heritage-house-prices-80a4732eae28.herokuapp.com/).

## Acknowledgements
- I acknowledge all the tutors and fellow students at [Slack](https://app.slack.com/client/T0L30B202/D03PENWED0F) for their guidance and assistance to complete Powdery Mildew Detection.
* I acknowledge [Precious Ijege](https://www.linkedin.com/in/precious-ijege-908a00168/) for mentor support and finishing touches.

[Back to Table of contents](#table-of-contents)