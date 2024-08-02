# Mortgage Bank Analysis Project

## Description

A banking institution requires actionable insights into mortgage-backed securities, geographic business investment, and real estate analysis. The goal is to identify potential monthly mortgage expenses for each region based on monthly family income and rental of the real estate. Additionally, a statistical model will be created to predict the potential demand in dollar amounts of loans for each region in the USA.

## Dataset Description

### Variables

| Variable              | Description                                                             |
|-----------------------|-------------------------------------------------------------------------|
| Second mortgage       | Households with a second mortgage statistics                            |
| Home equity           | Households with a home equity loan statistics                           |
| Debt                  | Households with any type of debt statistics                             |
| Mortgage Costs        | Statistics regarding mortgage payments, home equity loans, utilities, and property taxes |
| Home Owner Costs      | Sum of utilities, and property taxes statistics                         |
| Gross Rent            | Contract rent plus the estimated average monthly cost of utility features|
| High school Graduation| High school graduation statistics                                       |
| Population Demographics| Population demographics statistics                                     |
| Age Demographics      | Age demographic statistics                                              |
| Household Income      | Total income of people residing in the household                        |
| Family Income         | Total income of people related to the householder                       |

## Project Tasks

#### Data Import and Preparation
1. Import data.
2. Determine the primary key and the need for indexing.
3. Assess the fill rate of the variables and devise plans for missing value treatment. Explicitly explain the reason for the treatment chosen for each variable.

#### Exploratory Data Analysis (EDA)
1. Perform debt analysis:
   - Explore the top 2,500 locations where the percentage of households with a second mortgage is the highest and percent ownership is above 10 percent. Visualize using a geo-map. Set the upper limit for the percentage of households with a second mortgage to 50 percent.
   - Calculate bad debt using the equation:
     ``` 
     Bad Debt = P(Second Mortgage ∩ Home Equity Loan)
     Bad Debt = second_mortgage + home_equity - home_equity_second_mortgage
     ```
   - Create pie charts to show overall debt and bad debt.
   - Create box and whisker plots and analyze the distribution for second mortgage, home equity, good debt, and bad debt for different cities.
   - Create a collated income distribution chart for family income, household income, and remaining income.
2. Perform EDA and derive insights into population density and age:
   - Create a new field called population density using `pop` and `ALand` variables.
   - Create a new field called median age using `male_age_median`, `female_age_median`, `male_pop`, and `female_pop`.
   - Visualize the findings using appropriate chart types.
   - Create bins for population into a new variable with no more than 5 categories for ease of analysis.
   - Analyze the married, separated, and divorced population for these population brackets and visualize using appropriate chart types.
3. Detail observations for rent as a percentage of income at an overall level and for different states.
4. Perform correlation analysis for all relevant variables by creating a heatmap and describe the findings.

#### Data Pre-processing
1. Conduct factor analysis to find latent variables in the dataset and gain insight into the linear relationships in the data.
   - Obtain the common factors and plot the loadings.
   - Identify latent variables such as high school graduation rates, median population age, second mortgage statistics, percent own, and bad debt expense.

#### Data Modeling
1. Build a linear regression model to predict the total monthly expenditure for home mortgage loans.
   - Use the `deplotment_RE.xlsx` file, where `hc_mortgage_mean` is the predicted variable.
   - Exclude loans with NaN values for `hc_mortgage_mean`.
   - Run the model at a national level. If the accuracy and R square are not satisfactory, proceed to the state level.
   - Considerations for building the model:
     - Ensure variables have a significant impact on predicting monthly mortgage and owner costs.
     - Start with all predictor variables for the initial hypothesis.
     - Achieve an R square of 60 percent or above.
     - Ensure multi-collinearity does not exist among dependent variables.
     - Test if the predicted variable is normally distributed.

---
