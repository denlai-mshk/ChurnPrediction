## ChurnPrediction
Predict churn of a subscriber using a multi-input model to predict churn.
Read the full code story here.  (https://microsoft.com/developerblog)

## Business Problem

For a service business, there are two ways to drive growth: grow the number of new customers, or increase the lifetime value from the customers that you already have by retaining more of them. Improving customer retention requires the ability to predict which subscribers are likely to cancel, and to intervene with the right retention offers at the right time. Recently, the use of deep learning algorithms that learn sequential product usage customer behavior to make predictions have begun to offer businesses a more powerful method to pinpoint accounts at risk. This understanding of an account’s churn likelihood allows a company to act to save the most valuable customers before they churn.
 
Managing churn is fundamental to service businesses. The lifetime value of the customer (LTV) is the central measure of business value for a subscription business, with churn as the central input. It’s often calculated as Lifetime Value = margin * (1/monthly churn). Reducing monthly churn in the denominator increases the LTV of the customer base. With increased LTV for the customer base comes increased profitability, and with that increased profit comes the economic support to increase marketing activity investment in growing customer acquisition, completing a virtuous cycle for the business.

## Technical Problem Statement

Predicting that a customer is likely to churn requires understanding the patterns in user state and the sequence of user behavior for churners compared to non-churners. Modeling of these user states and behavioral sequences requires using tabular source data, coming from transaction systems, incident management systems, customer and product records, and then turning these data into a model-friendly set of numerical matrices. This pre-processing of the source tabular data into model-friendly sequences is in and of itself a significant piece of technical work.

For the prediction task we had to choose whether to predict against the attrition event itself or the inactivity that might presage a later attrition. In our modeling approach we predict churn itself. Despite the fact that the actual cancellation decision is a lagging indicator, our model delivered sufficient precision. In future modeling efforts, we will label long-standing inactivity as effective churn.

We defined with MAF a performance requirement in terms of accuracy, precision and recall. Once a model performed at the required levels, we could experiment with retention offers to those predicted to cancel, and to do so we needed to deploy this predictive model in a secure and operationally reliable environment where we could retrieve batch predictions daily and drive retention offers and the associated workflow.
