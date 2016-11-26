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
  - Zero(0) - The "variance" in the data is not explained by the model.
![screen shot 2016-11-26 at 2 27 36 pm](https://cloud.githubusercontent.com/assets/16644017/20638237/862277c8-b3e4-11e6-9be4-b448d987c795.png)
  

