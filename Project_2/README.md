# Project 2 - Ames Housing Data and Kaggle Challenge
---
### Introduction
---
We are tasked with creating a regression model based on the Ames Housing Dataset. This model will predict the price of a house at sale. 

### Problem Statement
---
There are oftentimes mismatch of expectations between homeowners and home buyers. Homeowners look to maximize on the value of their house and home buyers look to get the best features on a tight budget. This project aims to answer some of these questions:
- How can homeowners maximize the value on their house?
- What are the features that add the most value to the house?
- What kind of house or features would home buyers be able to afford based on their budget?
- How much should buyers be paying for houses with certain features?

The metrics that will be used for model selection are R2 and RMSE. Models that will be used in this project are linear regression, ridge regression, lasso regression and the elastic net regression.

This project is split into three Jupyter Notebooks, EDA and Cleaning, Preprocessing and Feature Engineering and finally, Model Testing and Tuning.

### Data Dictionary
--- 
|Attribute|Variable Type |Dataset|Description|
|---|---|---|---|
|**Id**|Discrete|Ames Housing|Unique ID for each property|
|**PID**|Nominal|Ames Housing|Parcel identification number  - can be used with city web site for parcel review|
|**MS SubClass**|Nominal|Ames Housing|Identifies the type of dwelling involved in the sale|
|**MS Zoning**|Nominal|Ames Housing|Identifies the general zoning classification of the sale|
|**Lot Frontage**|Continuous|Ames Housing|Linear feet of street connected to property|
|**Lot Area**|Continuous|Ames Housing|Lot size in square feet|
|**Street**|Nominal|Ames Housing|Type of road access to property|
|**Alley**|Nominal|Ames Housing|Type of alley access to property|
|**Lot Shape**|Ordinal|Ames Housing|General shape of property|
|**Land Contour**|Nominal|Ames Housing|Flatness of the property|
|**Utilities**|Ordinal|Ames Housing|Type of utilities available|
|**Lot Config**|Nominal|Ames Housing|Lot configuration|
|**Land Slope**|Ordinal|Ames Housing|Slope of property|
|**Neighborhood**|Nominal|Ames Housing|Physical locations within Ames city limits (map available)|
|**Condition 1**|Nominal|Ames Housing|Proximity to various conditions|
|**Condition 2**|Nominal|Ames Housing|Proximity to various conditions (if more than one is present)|
|**Bldg Type**|Nominal|Ames Housing|Type of dwelling|
|**House Style**|Nominal|Ames Housing|Style of dwelling|
|**Overall Qual**|Ordinal|Ames Housing|Rates the overall material and finish of the house|
|**Overall Cond**|Ordinal|Ames Housing|Rates the overall condition of the house|
|**Year Built**|Discrete|Ames Housing|Original construction date|
|**Year Remod/Add**|Discrete|Ames Housing|Remodel date (same as construction date if no remodeling or additions)|
|**Roof Style**|Nominal|Ames Housing|Type of roof|
|**Roof Matl**|Nominal|Ames Housing|Roof material|
|**Exterior 1st**|Nominal|Ames Housing|Exterior covering on house|
|**Exterior 2nd**|Nominal|Ames Housing|Exterior covering on house (if more than one material)|
|**Mas Vnr Type**|Nominal|Ames Housing|Masonry veneer type|
|**Mas Vnr Area**|Continuous|Ames Housing|Masonry veneer area in square feet|
|**Exter Qual**|Ordinal|Ames Housing|Evaluates the quality of the material on the exterior |
|**Exter Cond**|Ordinal|Ames Housing|Evaluates the present condition of the material on the exterior|
|**Foundation**|Nominal|Ames Housing|Type of foundation|
|**Bsmt Qual**|Ordinal|Ames Housing|Evaluates the height of the basement|
|**Bsmt Cond**|Ordinal|Ames Housing|Evaluates the general condition of the basement|
|**Bsmt Exposure**|Ordinal|Ames Housing|Refers to walkout or garden level walls|
|**BsmtFin Type 1**|Ordinal|Ames Housing|Rating of basement finished area|
|**BsmtFin SF 1**|Continuous|Ames Housing|Type 1 finished square feet|
|**BsmtFin Type 2**|Ordinal|Ames Housing|Rating of basement finished area (if multiple types)|
|**BsmtFin SF 2**|Continuous|Ames Housing|Type 2 finished square feet|
|**Bsmt Unf SF**|Continuous|Ames Housing|Unfinished square feet of basement area|
|**Total Bsmt SF**|Continuous|Ames Housing|Total square feet of basement area|
|**Heating**|Nominal|Ames Housing|Type of heating|
|**Heating QC**|Ordinal|Ames Housing|Heating quality and condition|
|**Central Air**|Nominal|Ames Housing|Central air conditioning|
|**Electrical**|Ordinal|Ames Housing|Electrical system|
|**1st Flr SF**|Continuous|Ames Housing|First Floor square feet|
|**2nd Flr SF**|Continuous|Ames Housing|Second floor square feet|
|**Low Qual Fin SF**|Continuous|Ames Housing|Low quality finished square feet (all floors)|
|**Gr Liv Area**|Continuous|Ames Housing|Above grade (ground) living area square feet|
|**Bsmt Full Bath**|Discrete|Ames Housing|Basement full bathrooms|
|**Bsmt Half Bath**|Discrete|Ames Housing|Basement half bathrooms|
|**Full Bath**|Discrete|Ames Housing|Full bathrooms above grade|
|**Half Bath**|Discrete|Ames Housing|Half baths above grade|
|**Bedroom AbvGr**|Discrete|Ames Housing|Bedrooms above grade (does NOT include basement bedrooms)|
|**Kitchen AbvGr**|Discrete|Ames Housing|Kitchens above grade|
|**Kitchen Qual**|Ordinal|Ames Housing|Kitchen quality|
|**TotRms AbvGrd**|Discrete|Ames Housing|Total rooms above grade (does not include bathrooms)|
|**Functional**|Ordinal|Ames Housing|Home functionality (Assume typical unless deductions are warranted)|
|**Fireplaces**|Discrete|Ames Housing|Number of fireplaces|
|**Fireplace Qu**|Ordinal|Ames Housing|Fireplace quality|
|**Garage Type**|Nominal|Ames Housing|Garage location|
|**Garage Yr Blt**|Discrete|Ames Housing|Year garage was built|
|**Garage Finish**|Ordinal|Ames Housing|Interior finish of the garage|
|**Garage Cars**|Discrete|Ames Housing|Size of garage in car capacity|
|**Garage Area**|Continuous|Ames Housing|Size of garage in square feet|
|**Garage Qual**|Ordinal|Ames Housing|Garage quality|
|**Garage Cond**|Ordinal|Ames Housing|Garage condition|
|**Paved Drive**|Ordinal|Ames Housing|Paved driveway|
|**Wood Deck SF**|Continuous|Ames Housing|Wood deck area in square feet|
|**Open Porch SF**|Continuous|Ames Housing|Open porch area in square feet|
|**Enclosed Porch**|Continuous|Ames Housing|Enclosed porch area in square feet|
|**3Ssn Porch**|Continuous|Ames Housing|Three season porch area in square feet|
|**Screen Porch**|Continuous|Ames Housing|Screen porch area in square feet|
|**Pool Area**|Continuous|Ames Housing|Pool area in square feet|
|**Pool QC**|Ordinal|Ames Housing|Pool quality|
|**Fence**|Ordinal|Ames Housing|Fence quality|
|**Misc Feature**|Nominal|Ames Housing|Miscellaneous feature not covered in other categories|
|**Misc Val**|Continuous|Ames Housing|Dollar-Value of miscellaneous feature|
|**Mo Sold**|Discrete|Ames Housing|Month Sold (MM)|
|**Yr Sold**|Discrete|Ames Housing|Year Sold (YYYY)|
|**Sale Type**|Nominal|Ames Housing|Type of sale|
|**SalePrice**|Continuous|Ames Housing|Sale price $$ (target)|

### Conclusion and Recommendations
---
The elastic net model turned out to have the best predictive performance as compared the the other linear models. Features that are highlighted to be the most important revolve around square area, location, condition and age of the house. However, the model does come with its own set of limitations. The dataset is limited in its own time frame captured and its location. It does not capture changes that could arise due to black swan events, such as COVID-19. The model is also only limited to predicting house prices in Ames, which may have varying geographical and demographical differences as compared to other places in the world.

