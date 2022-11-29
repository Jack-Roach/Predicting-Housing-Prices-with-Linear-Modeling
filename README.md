# **Predicting Housing Prices using Linear Modeling**
## By Jack Roach
#### Copy of my repository from my time in General Assembley's Data Science Immersive Course
## Problem Statement
#### You work for a real estate investment firm that wants to flip houses in Ames, Iowa. Your goal is to maximize the returns on your company's real estate investments by deciding what attributes contribute most to property value in this region and therefore which housing attributes are worth improving. In the interest of helping people trying to flip houses in Ames, Iowa, what housing and property features contribute most to a house's value?
## Datasets Utilized
### The original datasets obtained from the Ames Assessor's Office in Ames, Iowa
[train.csv](https://git.generalassemb.ly/jackroach/project-2/blob/main/datasets/train.csv)
[test.csv](https://git.generalassemb.ly/jackroach/project-2/blob/main/datasets/test.csv)

### We cleaned the datasets so that they may be utilized for creating house pricing models more effectively
[train_cleaned.csv](https://git.generalassemb.ly/jackroach/project-2/blob/main/datasets/train_cleaned.csv)

[test_cleaned.csv](https://git.generalassemb.ly/jackroach/project-2/blob/main/datasets/test_cleanedtest.csv)

## Data Dictionary
Further reading on the Ames, Iowa housing dataset [here](http://jse.amstat.org/v19n3/decock.pdf)
### Online Data
[Dictionary for Original Dataset](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)
### Custom Features
|Feature|Type|Description|
|---|---|---|
|**Age**|*Float*|Age of the house based on when it was sold from when it was built|
|**Garage Age**|*Float*|Age of the house's garage (if applicable) based on when the house was sold from when the garage was built|
|**Has Garage**|*Binary*|1 = Property has a garage, 0 = Property does not have a garage|
|**after2000**|*Binary*|1 = House was built after the year 2000, 0 = House was built before the year 2000 |

## Solving the Problem Statement

Based on our linear model (refer the end of Modeling.ipynb), the strongest categorical feature in a real estate listing's value in Ames, Iowa is the neighborhood that a property is located in. Holding all other variables constant, if a house is located in the Green Hills neighborhood, its value increases by approximately $\$$128,597 compared to its value if it was located in Bloomington Heights, the baseline neighborhood for our model, assuming all other variables are constant. On the contrary, a house's value decreases by approximately $\$$13,803 compared to the baseline if it is located in the Sawyer West neighborhood.

The strongest numerical feature in a real estate listing's value is the Exterior Quality Score, ranging from poor to best indicated by an ordinal scale of 0 to 4. Holding all other variables constant, for every 1 point a house's exterior quality score increases, its value increases by approximately $\$$13,080.

Let's look at a few more coefficients from our model:
- Sale Type - Holding all else in our model constant, a house sold through a contract that involves a 15% down payment is going to be worth $\$$63,241 more than if its sale type was the baseline, the sale being through a court officer Deed/Estate
- Zoning Classification of the Sale - A property whose zoning is classified as Industrial is going to sell for $\$$49,982 more than a property with the baseline zoning classification, Agriculture, holding all else constant
- Primary Exterior Covering on House - A house with cinderblocks as the primary exterior cover is worth $\$$38,827 more than a house with the baseline primary exterior cover, Asbestos Shingles, holding all else constant

### Additional Recommendations:
- Improve the quality of fireplaces in the property, houses with the highest rated fireplaces (nominal score of 5) are worth $\$$3,970 more than houses with average quality fireplaces (nominal score of 3) holding all else constant.
- Rennovate the kitchen - Houses with excellent kitchen quality (nominal score of 5) increase in value by $\$$20,934 compared to houses with average quality kitchens (nominal score of 3), holding every other feature constant.
- Consider adding a stone styled masonry veneer, this increases a house's value by $\$$29,266 compared to the baseline masonry veneer type, common brick.
- Invest in houses with a foundation made out of slab, they are worth approximately $\$$8,042 more than houses with foundations made out of brick and tile.
- Houses built near positive off-site features such as parks and green belts are worth $\$$23,023 more than houses located adjacent to Arterial street.

### Recommendations we can make without needing to generate a model
- The Overall Quality score of the material and finish of the house has the greatest correlation with Sales Price out of any of our numerical features, improving this the safest bet to increasing a house's value. In our model, this score increases the value of a house by $\$$9,040 per point on a scale of 1 - 10, holding all other variables constant.

### Further Steps
Further steps should be taken to map out the city of Ames in order to more accurately identify key real estate locations, landmarks, and relevant places of interests that could affect housing prices in ways unaccounted for by the data set.

Housing data was taken from the years 2007 to 2010 was a tumultuous time for the housing market. House prices recorded during these years could potentially be abnormally low or high depending on the date each property was sold relative to the market crash of 2008 caused by the subprime mortage crisis. Additional data should be collected from more recent years in order to reduce potential bias from market turmoil and to modernize the data so it is more applicable to the 2022 housing market.