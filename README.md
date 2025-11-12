# [Python] Customer Segmentation with RFM Analysis
## I. Introduction
### 1. About RFM Model and Segmentation Approach
- RFM is a marketing analysis technique that stands for Recency, Frequency, and Monetary Value.
  - ***Recency***: measures how recently a customer has made a purchase.
  - ***Frequency***: measures how often a customer has made purchases.
  - ***Monetary***: measures the total amount of money a customer has spent on purchases.
    
- Based on the RFM model, customers were segmented into distinct groups according to their purchasing behavior and engagement level.
- Segmentation Approach
  - The RFM model assigns each customer a score for Recency (R), Frequency (F), and Monetary (M) based on their purchase history.
  - Customers were then grouped into segments using quantile-based ranking (quintile method), where higher scores indicate more recent, frequent, and valuable transactions.
  - By combining these three dimensions, we identified key behavioral segments that reflect different stages of the customer lifecycle.

| Segment Name | Description |
| ------------ | ----------- |
| Champions | High Recency, High Frequency, High Monetary |
| Loyal Customers | Medium Recency, High Frequency, Medium Monetary  |
| Potential Loyalists | High Recency, Medium Frequency, Medium Monetary |
| At-Risk Customers | Low Recency, High Frequency, High Monetary |
| Hibernating Customers | High Recency, Low Frequency, Low Monetary |
| New Customers | High Recency, Medium Frequency, Medium Monetary |
| Lost Customers | Very low Recency and Frequency |

### 2. Business Questions
- SuperStore is a nationwide retail company that offers a wide range of products across categories such as office supplies, furniture, and technology. With a large and diverse customer base, SuperStore continuously aims to enhance customer engagement and loyalty through data-driven strategies.
- The Marketing Department aims to launch campaigns to appreciate loyal customers who have supported the company over time, as well as to identify potential customers who could become loyal ones.
- The Marketing Director proposed using the RFM model to segment customers and would like to determine which of the three metrics — Recency, Frequency, or Monetary — plays the most decisive role?

## II. Data Visualization with Python and Insights
### 1. UK Market
- Top 10 Countries with the largest revenue

- Distribution of Recency, Frequency, Monetary
- The boxplot of Recency by Segment
- The heatmap of Average Monetary by Recency (R) and Frequency (F)
- Scatter Plot – Recency vs Monetary by Segment
- Bar Chart – Customer Count by Segment
- Total Rev | Average Rev | Proportion of Rev by Customer Segment
- Line Chart - Revenue Trend Over Time



### 2. Non-UK Market
- Proportion of UK vs Non-UK Revenue
- Top 10 Non-UK Countries Largest Revenue
- Customer Count by Segment
- Total Revenue by Customer Segment
  
## III. Recommendations
- For the Marketing team of SuperStore, the most important indicator among the
three RFM metrics is Recency (R).
- While Frequency (F) and Monetary (M) provide valuable insights into customer
loyalty and spending power, Recency is the most actionable metric for
marketing — it helps prioritize timely, targeted communication to maximize
campaign effectiveness and prevent customer churn.
- Some recommendations for each segment customers group as below:
  | Segments | Characteristics | Recommendations |
  | -------- | --------------- | --------------- |
  | Active Customers | High purchase frequency and recency, strong engagement with the brand | Maintain engagement through exclusive offers, early access, and personalized loyalty programs to retain their high-value contribution |
   
 
| **Segments** | **Characteristics** | **Recommendations** |
|---------------|----------------------|----------------------|
| **Active Customers** <br> • Champions <br> • Loyal <br> • Potential Loyalists | High purchase frequency and recency, strong engagement with the brand. | Maintain engagement through exclusive offers, early access, and personalized loyalty programs to retain their high-value contribution. |
| **At-Risk Customers** <br> • Need Attention <br> • About to Sleep <br> • At Risk | Declining purchase frequency and recency, showing early signs of disengagement. | Use targeted win-back campaigns, personalized discounts, and reminders to re-engage them before churn increases. |
| **Inactive Customers** <br> • Hibernating <br> • Lost Customers | Very low or no recent activity, likely churned. | Launch reactivation campaigns with strong incentives or gather feedback to understand why they left. |

