# advanced-analytics
Advanced Analytics

### Numeric & Non-Numeric Outcomes (scenario examples)
1. Tricycle Manufacturer. A company wants to use historical production data to know how many tricycles they'll need to produce over the next 6 months to meet the expected demand.
  - Since the outcome the manufacturer wants to predict is a number, then the target variable is numeric.
  - Therefore, they would use a NUMERIC, or REGRESSION, model to solve this problem.
  
2. Hot and Fresh Pizza wants to use sales data from their existing stores, and respective demographic data around those stores, to PREDICT how many piazzas they'll sell at their new store location.
  - Since the outcome Hot and Fresh Pizza wants to PREDICT is the number of pizzas, then the target variable is numeric.
  - Therefore they would use a numeric, or regression, model to solve the problem.
  
3. A bank wants to use historica data of their clients  to PREDICT whether a new customer will default on a loan, always pay on time, or sometimes pay. 
  - Since the outcome the bank is trying to predict is a CATEGORY that the new customer will fall into, they would use NON-NUMERIC, or CLASSIFICATION, models to solve this problem.
  
### Numeric Models
![screen shot 2016-11-24 at 11 41 30 pm](https://cloud.githubusercontent.com/assets/16644017/20602217/9c67ad50-b29f-11e6-89bc-bf3884dfa81c.png)
- Continuous
  - A continuous variable is one that can take on all values in a range. For instance your height can be measured down to many decimal places. We do not grow in even inch intervals.
- Time-Based
  - A time-based numeric variable is one where you are trying to predict what will happen over time. This is often related to forecasting.
- Count
  - Count variables are numbers that are discrete, positive integers. They’re called count numbers because they’re used to analyze variables that you can count. As modeling these type of variables is not common in business, we won’t be covering this topic in this course.

### Non-Numeric Models (Non-Numeric target variables)
- E.g. Is an electronic device going to fail after 1000 hours or not?;
- E.g.2 Is the customer going to pay on time, default, or late on a payment?;
- Binary Vs. Non-Binary
  - Binary. Only 2(two) possible categorical outcomes.
    - True or False;
    - Yes or No;
  - Non-Binary. More than 2 possible categorical outcomes.
    - Small, Medium, Large;
    - Pay on time, default, or late;

### Linear Regression Validation
- Correlation Validation
  - We evaluate our dataset to point out if it has good correlation (either positive or negative)
  - Closer to 1(one) - Strong positive correlation;
  - (0)Zero - No correlation;
  - Closer to -1(minus one) - Strong negative correlation;
![screen shot 2016-11-26 at 12 21 58 am](https://cloud.githubusercontent.com/assets/16644017/20629365/7f174ee8-b36e-11e6-8d9d-187b7bca90b3.png)
- Coefficient of Determination (r-squared)
  - We evaluate our dataset to identify the **percent of variance that is explained by the model.**
  - Closer to 1(one) - The "variance" is explained by the model.
  - When Above .7(70%) - The variance in the data is considered good and explained by the model.
  - When between .3(30%) and .5(50%) - The variance in the data is considered okay.
  - When below .3(30%) - The variance in the data is considered as week and not explained by the model.
  - Zero(0) - The "variance" in the data is not explained by the model.
![screen shot 2016-11-26 at 2 27 36 pm](https://cloud.githubusercontent.com/assets/16644017/20638237/862277c8-b3e4-11e6-9be4-b448d987c795.png)
- Example #1:
![screen shot 2016-11-26 at 2 44 21 pm](https://cloud.githubusercontent.com/assets/16644017/20638306/dbe7ef9c-b3e6-11e6-9123-2fa6a13ceb2c.png)
  - a. Based on the r-squared value, how strong is this model?
    - Using Excel or Google Spreadsheet's RSQ function the answer is **0.7862**
    - **0.7862** is considered good as is above .7(70%).
    - We can consider the data to have a strong positive correlation.
  - b. Using the regression results, how many tickets per week could we expect from a new client with 525 employees?
    - Using Excel or Google Spreadsheet's linear regreesion calculation method (i.e. slope and y-intercept);
    - The linear regression equation is y = 0.181736 * x - 7.54648;
    - With this equation we can predict, through the model, that a new client with 525 employees will have about **87.8648** rounding to approximately 88 tickets/week.

### Multi-linear Regression (Using more data to strength the correlation coefficient)
- Transition from Linear to Multi-linear model:
![screen shot 2016-11-26 at 3 56 30 pm](https://cloud.githubusercontent.com/assets/16644017/20638671/f78d5688-b3f0-11e6-9c76-36e9cb113b20.png)
- Adding one more variable (Value of contract) this is how the equation will be:
![screen shot 2016-11-26 at 3 57 37 pm](https://cloud.githubusercontent.com/assets/16644017/20638676/2fc85c50-b3f1-11e6-914e-3a766ea4bdcb.png)

#### Simple example
- Using Excel Data Analysis Toolpak.
- Running Regression analysis we have the following result:
![screen shot 2016-11-26 at 11 48 02 pm](https://cloud.githubusercontent.com/assets/16644017/20641074/09ed73ca-b433-11e6-898e-087775bfb620.png)
- So according with the following scenario:
  - What would the model predict for the number of tickets for a customer with 750 employees and a contract of $13,000?
  - The correct answer is **61 (sixty-one)**.
  - Because using the Coefficients we have the formula: **NO.of Ticket = -24.26671247 + 0.101907277 x NO.of Employees + 0.00066845 x Value of Contract**

>"Using both predictor variables, in this example, resulted in a better model with a higher level of correlation

### Multi-linear regression with Categorial variable (Transforming categorial variables)

#### Using Dummy Variables:
- Now we didn't create a variable for northeast. That’s because the equation needs a baseline value that is not coded into a dummy variable. If a state is in the northeast, then the value for all three of the dummy variables would be zero. You always create one less dummy variable than the number of categories to make sure that one category is represented by zero values for the dummy variables. That one category, in this case the northeast region, becomes the category that others are compared to.

#### Bad Example:
![screen shot 2016-11-27 at 3 33 52 pm](https://cloud.githubusercontent.com/assets/16644017/20646095/f2264f12-b4b6-11e6-8cda-ad4262788fc1.png)
- Region is a categorical variable with four values: **west, midwest, northeast, and southeast**. You assign them the numbers **1, 2, 3, and 4** respectively, and run the model.
- (Formula) *Expenditures = -530 + 0.073 Avg_Income + 1406.36 Pct_Under_18 + 6.53 region*
- **The problem here is that:** The coefficient on region implies that for every increase in one region, the state spends about $6.52 more per pupil. Now this one doesn't make logical sense. There was no logical order in the numbers, and this format doesn't allow us to take into account enough of the variation among regions.
- i.e. We're assuming that all regions are being seen as one, instead of individually.

#### Good Example:
![screen shot 2016-11-27 at 4 22 41 pm](https://cloud.githubusercontent.com/assets/16644017/20646515/c15ef60c-b4bd-11e6-9135-da5c549a6df3.png)
- Each of the variables takes on a value of either 1 or 0. If the state is in the southeast, then the value for the southeast variable would be 1 while the other two variables would be zero.
- Basic example:
  - (Formula) *School exp = -468 + (0.067 x avg income) + (1349 x pct under 18) - (14.4 x midwest) - (9.3 x southeast) + (16.5 x west)*
  - What is the school's predicted expenditure in a state with an average income of $4,011, with the pop % under 18 of 32.5%, and is in the region 1(northeast)?
  - The answer is **342.91**


### Building the Model on Alteryx
- 1. Input tool (File);
- 2. Predictor Tool > Regression
   - Target Variable: Average Number of Tickets.
   - Predictor Variables: Numer of Employees, Value of Contract, and Industry.
![screen shot 2016-11-27 at 5 49 33 pm](https://cloud.githubusercontent.com/assets/16644017/20646949/ec6b1590-b4c9-11e6-9848-790d11a011cd.png)
- 3. Interpreting the Linear Regression
![screen shot 2016-11-27 at 5 51 22 pm](https://cloud.githubusercontent.com/assets/16644017/20647007/828ede66-b4cb-11e6-833a-933347fb1eb9.png)
  - There are three values that are of particular importance. The **coefficient estimates, the p-values, and the R-squared**.
  - Coefficient Estimates:
    - Represent the magnitude of the relationship between each predictor variable and the target variable;
    - E.g. The coefficient on the number.of.employees means that each additional employee will lead to roughly an additional 0.1 tickets
  - P Value:
    - Probability that observed results (the coefficient estimate) occurred by chance, and that there is no actual relationship between the predictor and target variable;
    - Is probability that the coefficient is zero;
    - The lower the p-value the higher the probability that a relationship exists between the predictor and target variable.
    - If the p-value is high, we should not rely on the coefficient estimate.
    - When a predictor variable has a p-value below 0.05, the relationship between it and the target variable is considered to be statistically significant. 
    - The (asterisks/stars) to the right indicate *Statistical Significance*
    - In our example, we see that our predictor variables are significant, with the number of employees and the value of the contract being the most significant.
    - Generally, we’ll want to remove variables from the model that are not statistically significant predictors of the target variable.
  - R-Squared:
    - R-squared ranges from 0 to 1 and represents the amount of variation in the target variable explained by the variation in the predictor variables. 
    - The higher the r-squared, the higher the explanatory power of the model.
    
### Final example:
#### Evaluate the following equation:
- The new client has 732 employees, with a contract value that is worth $825,000, and is in the services industry. 
- Your company currently has 23 help desk resources on staff, and each resource has a capacity of 125 tickets per week. 
- The current average number of tickets that the help desk has been receiving is 2800 per week.

#### Question:
Given the current capacity of the help desk, how many additional people would the help desk need to hire to handle the expected increase in support tickets?

#### Multi-linear regression equation:
Average No. of tickets = -18.45 + (0.1116 x NO.of employees) + (0.0004757 x Value of Contract) + (-8.725 x Industry Retail) + (12.49 x Industry Services);

#### Solution:
1. Calculate predicted No.of tickets increase with new customer: approx.: **476**
2. Calculate current Help Desk task handling balance: 75 task over capacity (2875 H.Desk capacity - 2800 Cur.task AVG per week)
3. Divide (New upcoming tasks prediction / Individual H.Desk capacity) = (401 / 125)
4. The result is: **3.2121**.
5. Since we can't have help desk shortage, then we round the number to **4.0**.
6. Additionally, the over Help desk capacity will be **(0.8 x 125) = 100 over capacity**;
