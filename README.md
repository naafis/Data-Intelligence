# Data Intelligence Project

This project focuses on [brief description of the project's purpose and goals].

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Installation
1. Clone the repository:

### Data Set Information:

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were 
based on phone calls. Often, more than one contact to the same client was required, in order to access if the product 
(bank term deposit) would be ('yes') or not ('no') subscribed.

## Attribute Information

### Bank client data:

- Age (numeric)
- Job : type of job (categorical: 'admin.', 'blue-collar', 'entrepreneur', 'housemaid', 'management', 'retired', 
'self-employed', 'services', 'student', 'technician', 'unemployed', 'unknown')
- Marital : marital status (categorical: 'divorced', 'married', 'single', 'unknown' ; note: 'divorced' means divorced 
or widowed)
- Education (categorical: 'basic.4y', 'basic.6y', 'basic.9y', 'high.school', 'illiterate', 'professional.course', 
'university.degree', 'unknown')
- Default: has credit in default? (categorical: 'no', 'yes', 'unknown')
- Housing: has housing loan? (categorical: 'no', 'yes', 'unknown')
- Loan: has personal loan? (categorical: 'no', 'yes', 'unknown')

### Related with the last contact of the current campaign:

- Contact: contact communication type (categorical:
'cellular','telephone')
- Month: last contact month of year (categorical: 'jan', 'feb', 'mar',
…, 'nov', 'dec')
- Day_of_week: last contact day of the week (categorical:
'mon','tue','wed','thu','fri')
- Duration: last contact duration, in seconds (numeric). Important
note: this attribute highly affects the output target (e.g., if
duration=0 then y='no'). Yet, the duration is not known before a call
is performed. Also, after the end of the call y is obviously known.
Thus, this input should only be included for benchmark purposes and
should be discarded if the intention is to have a realistic
predictive model.

### Other attributes:

- Campaign: number of contacts performed during this campaign and for
this client (numeric, includes last contact)
- Pdays: number of days that passed by after the client was last
contacted from a previous campaign (numeric; 999 means client was not
previously contacted)
- Previous: number of contacts performed before this campaign and for
this client (numeric)
- Poutcome: outcome of the previous marketing campaign (categorical:
'failure','nonexistent','success')

### Social and economic context attributes:

- Emp.var.rate: employment variation rate - quarterly indicator
(numeric)
- Cons.price.idx: consumer price index - monthly indicator (numeric)
- Cons.conf.idx: consumer confidence index - monthly indicator
(numeric)
- Euribor3m: euribor 3 month rate - daily indicator (numeric)
- Nr.employed: number of employees - quarterly indicator (numeric)

### Output variable (desired target):
y - has the client subscribed a term deposit? (binary: 'yes', 'no')


## Task 1
A large bank has asked us to evaluate the marketing algorithms they use for retail banking. Their sophisticated phone 
marketing algorithm predicts whether a certain person will subscribe to a term deposit or not. Based on that 
assessment, the bank then optimises its phone calling strategy. With this algorithm, the bank has been successful in 
predicting which clients are more likely to subscribe to their term deposits. 

Management is now interested in finding out how a classification model can lead to certain decision-making processes. 

- Create a classification model in Python. Feel free to use libraries such as SkLearn, Keras/Tensorflow or Pytorch. 
- Analyse the model and provide insight into which features/variables influence the outcome of the classification the 
most: on a global level, and specifically for observation #4 and #20.
- Develop some form of plot or graph with brief comments on your observations. 

Heads up! Jakob left you a voice message to help you with this task.

 
“Hi there,

Thanks for helping with the task. And don’t worry too much about the performance of the model. What’s important is that 
you create a classification model and that you try to evaluate the relevance of potential features, both on a global 
and a local level.

Getting familiar with the Lime and SHAP libraries will help.

Thanks and catch you later.”

## Task 2

Today, credit is no longer limited to classical bank loans. The rise of e-commerce has increased the demand for new and 
more flexible credit solutions. The increased demand has been met by new companies from the fintech sector that offer 
easily accessible online loans to a wide audience. These new business models offer simple solutions, such as flexible 
payment schedules or buy-now-pay-later, that can be accessed with just a few clicks. 

Online merchants also need new ways to procure capital to manufacture their products, as they receive payment only 
after their product has been sold. In order to meet increasing demand, new credit offerings have emerged. Repayment of 
these loans is no longer based on a fixed schedule but instead depends directly on online sales. The loan is paid back 
in instalments with every sale, and thus payments depend directly on the sales volume. 

Predicting the future cash flows needed for the valuation of a portfolio consisting of these merchant loans is 
challenging.

Our client is a large global online lending platform that provides loans to both consumers and merchants. These 
instruments are classified as assets on the balance sheet. 

Our audit colleagues have asked for our help to ensure the balance sheet values are correct. The value of the loan 
portfolio depends on future cash flows, which are stochastic. 

Our job is to ensure that the client’s portfolio has been valued correctly.

As part of the quantitative finance team, you and Jakob prepare a PowerPoint document containing the results of your 
portfolio valuation.

As you are supporting the audit colleagues with the audit for the year 2020, the value of the portfolio shall be 
determined as of 31 December 2020. The following steps will guide you through the valuation:

- Inspect the historical data provided by the client. The data ranges from June 2019 until December 2020. Every month 
constitutes a vintage and the data includes the loan amount that was originated per vintage, as well as the repayments 
that have been observed up until and including December 2020 (the vintages are given as rows and the columns specify 
the period of the repayment). 
- Based on the provided data, compute the historical repayment percentages, i.e. every repayment’s share of the 
origination amount. 
- Compute the expected repayment percentages for all vintages over the lifetime of the loans.
- From the expected repayment percentages, compute the forecasted cash flows using the origination amounts.
- Using the assumed discount rate, derive the present value of the forecasted cash flows and of the portfolio. Don’t 
forget to convert the annual interest rate to a monthly interest rate.
- The client’s estimate of the portfolio value was CHF 84’993’122.67. How close is this to your own estimate? Compute 
both the absolute and relative difference. Jakob tells you that the audit team considers any difference smaller than 
CHF 500’000 to be acceptable given the size of the portfolio. Based on the result of your valuation, conclude whether 
the difference to the client’s estimate falls below his threshold.

Jakob notes: The portfolio value should be rounded to two decimal places. The slides can be simple as we'll use them 
internally first. Focus on correct solutions to set up the team with the right insights.

### Assumptions

1. All cash flows are assumed to be paid back over a period of 30 months. Following this assumption, the last cash flow 
for the July 2020 vintage will be collected in December 2022 and thus there are 24 months that need to be forecasted 
(from January 2021 until December 2022).
2. Let 𝑝<sub>𝑖</sub> denote the expected repayment percentage as a share of the origination amount. For the portfolio valuation, 
assume that the expected repayment percentages are calculated as follows:


For the origination month, 𝑖 = 1, the value is already known and fed in. The same holds true for the following 
month, 𝑖 = 2, except for the last vintage, December 2020, where 𝑝<sub>2</sub> has not yet been observed. For this vintage, 
assume that the expected repayment percentage for 𝑖 = 2 will be twice the repayment of the first period 
(𝑝<sub>2</sub> = 2𝑝<sub>1</sub> for the December 2020 vintage).

From the third month until the forecast horizon, 3 ≤ 𝑖 ≤ 30:

![Equation](https://latex.codecogs.com/png.image?\dpi{110}\bg{white}&space;p_i=\max\left\{p_2\cdot\ln\left(1&plus;\left(1-\frac{i-1}{30}\right)\cdot\left(1-\sum_{j=1}^{i-1}p_j\right)\right),0\right\})

3. Assume that the forecasted cash flows are discounted with an annual rate of 2.5%.