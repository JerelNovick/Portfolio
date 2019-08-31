# Project 2 - Analysis of Ames Housing Data


## Description

The through the analysis of past data, a linear regression model was that would best predict sales prices of houses in Ames, Iowa.  The model was built on a dataset that contains the actual prices that houses were sold at.  Further information on the data can be found in the section below.  The model against a similar dataset to predict sale prices.  The predicted sale prices were submitted to Kaggle were they compared against the actual sale prices.

## Data

The data was provided in two separate CSV files.  The training dataset contained 2,051 rows each representing a transaction.  The dataset also had 81 columns that each represented an attribute (variable) of the property that was sold.  Similarly, the test data contained 879 rows and 80 columns.  The difference in columns between the two datasets is that the test dataset did not contain the sale prices that would be predicting.

A detailed description of each of the attributes can be found at http://jse.amstat.org/v19n3/decock/DataDocumentation.txt.

## Cleaning and Preparing Data

After importing the training data into Python, the column titles were standardized by making them all lower case and replacing any spaces with underscores (_).  All varaibles were then reviewed for missing or null values.  Missing numeric values were replaced with zeros.  Non-numeric or string values that were missing were replaced with "none".

The following columns were removed in order to slim the dataset:

        * Alley
        * Pool
        * Miscellaneous Features
        * Utilities
        * Basement Exposure
        * Basement Condition
        * Central Air Conditioning
        * Electrical
        * Exterior Condition
        * Fireplace Quality
        * Home Functionality
        * Garage Quality and Condition
        * Kitchen Above Grade
        * Street
        * Condition 1 and 2
        * Roof Material
        * Land Contour
        * MS Subclass
        * Heating
        * Basement Square Footage
        * Land Slope
        * Low Quality Square Footage
        * Sale Type

The columns were removed because they either had too many missing values or all or most  of the properties had the same attributes (ex: only two properties did not have all public utilities).

The following columns were added as interaction variables:

        * House Age - The difference between the year the property was sold and it was built.
        * Remodel Years - The difference between the year the property was renovated and it was built.
        * Total Bath Rooms - The sum of all full and half bath rooms in the house.
        * Total Outdoor Space - The sum of the square footage of porches or decks at the property.
        * Price Per Square Foot - The sale price of the house divided by its total square footage.
        * Logarithm of Sale Price - The natural logarithm of the sale price.
        
The changes were made to both of the datasets and saved under new names.  The final cleaned datasets had 58 and 56 columns, respectively.

## Exploratory Data Analysis (EDA)


After importing the cleaned test set, analysis began on many of its attributes.  The Python profile report provided a snap shots and histograms of all of the variables.  Further analysis was conducted on some of the other variables.  This included:

        * Creating a distribution curve of sale prices to visualize the level of skew.
        * Correlation matrices and heatmaps of the sale price against all of the numeric variables.
        * Scatter plots of the sale price against lot area, basement size, the age of the house and outdoor space.
        * Boxplots of sale prices against the number of bath rooms, bed rooms and garage size.
        * A bar chart showing the number of house sold in each neighborhood.

Some of what the information derived was :

        * There is a negative correlation betwen the age of the house when it was sold and its price.
          As the age increases the sale price tends to decrease.
        * The distribution of prices increases as the size of the house increases.
        * The majority of house were sold in the North Ames neighborhood.
        

## Modeling

Experimentation was conducted on a number of different modeling techniques and variables to produce 21 models.  Variables of high and low correlations were combined.  In addition, some dummy variables were created for non-numeric variables such as neighborhood and a properties qualities.  Since most of the variables were in different units, a standarized scale was applied to the,.  Furthermore, Ridge and Lasso regularization were employed

## Results

Models created had R-squared scores from 0.73 to 0.93.  For most of the models, residuals were tightly clustered at lower prices but became widely dispersed at higher prices.  The successful model produced a score of 23,133.30.  A mix of high and low correlation variables were used along with the natural logarithm of the sale price.
