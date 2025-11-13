# [Python] Customer Segmentation with RFM Analysis
## I. Introduction
### 1. About RFM Model and Segmentation Approach
- RFM is a marketing analysis technique that stands for Recency, Frequency, and Monetary Value.
  - ***Recency***: measures how recently a customer has made a purchase.
  - ***Frequency***: measures how often a customer has made purchases.
  - ***Monetary***: measures the total amount of money a customer has spent on purchases.
   <img width="919" height="475" alt="Image" src="https://github.com/user-attachments/assets/815f58b2-d524-4b10-b573-c8ca48272674" />
   
                                     Photo from Ambassador

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

   <img width="914" height="419" alt="Image" src="https://github.com/user-attachments/assets/a01098ce-8321-47c5-a0f1-52e029d64aac" />
   
                                             Photo from Ambassador

### 2. Business Questions
- SuperStore is a nationwide retail company that offers a wide range of products across categories such as office supplies, furniture, and technology. With a large and diverse customer base, SuperStore continuously aims to enhance customer engagement and loyalty through data-driven strategies.
- The Marketing Department aims to launch campaigns to appreciate loyal customers who have supported the company over time, as well as to identify potential customers who could become loyal ones.
- The Marketing Director proposed using the RFM model to segment customers and would like to determine which of the three metrics — Recency, Frequency, or Monetary — plays the most decisive role?

## II. Data Visualization with Python and Insights
### 1. UK Market
- **Top 10 Countries with the largest revenue**
![Image](https://github.com/user-attachments/assets/ecaa1448-dd71-430a-9e12-a30f6b875724)

  - The chart clearly shows that the United Kingdom overwhelmingly dominates
the company’s total revenue($9,025,222), contributing far more than any other
country. This indicates that the UK market is the primary revenue driver for
SuperStore, while other countries such as the Netherlands, EIRE, Germany, and
France contribute only marginally.
  - Given this imbalance, it is essential to separate the UK data from the rest of the
markets for deeper analysis.

- **Distribution of Recency, Frequency, Monetary**
![Image](https://github.com/user-attachments/assets/4f3852d5-1d00-4bfb-a7ff-1f29be9daae6)

![Image](https://github.com/user-attachments/assets/f71a2adc-d3bb-43b1-be67-874c186604fc)

![Image](https://github.com/user-attachments/assets/3af7daf3-4ac9-45a8-81dc-d354f41118bf)

  - The Frequency histogram indicates that the majority of customers have made
only one or two purchases, while a small subset exhibits much higher purchase
frequencies.
  - The Monetary distribution reveals that most customers generate relatively low
spending, while a few high-value customers contribute disproportionately large
revenue. The business has a core group of premium customers with high
monetary value.
  - The distribution of Recency shows a highly right-skewed pattern, indicating that
a large portion of customers made their last purchase recently (within the
past 50 days). This suggests that SuperStore maintains strong engagement with
many active customers.

- **The boxplot of Recency by Segment**
![Image](https://github.com/user-attachments/assets/525a069a-943b-404e-8151-6c6621ee8c62)

  - Champions, Loyal, and Potential Loyalists have the lowest recency values,
meaning they have purchased very recently and are highly engaged with the
store.
  - In contrast, At Risk, Cannot Lose Them, Hibernating Customers, and Lost
Customers show very high recency scores, indicating long inactivity periods
and a higher chance of churn.
  - Intermediate segments like Promising or Need Attention still show moderate
recency, suggesting they can be reactivated through targeted campaigns
before they become inactive.

- **The heatmap of Average Monetary by Recency (R) and Frequency (F)**
![Image](https://github.com/user-attachments/assets/528b6f81-0392-48c3-8186-d3960029c820)

  - Customers with high frequency (F=5) and high recency (R=5) generate the
highest average monetary value, reaching over $8,209, confirming their strong
and consistent buying behavior.
  - Conversely, customers with low frequency and low recency contribute the
least revenue, often below $550 on average.
  - The chart also reveals a significant disparity between the top quintile (score 5) and the other groups, suggesting that a small portion of highly active
customers accounts for a disproportionately large share of total revenue.

- **Scatter Plot – Recency vs Monetary by Segment**
![Image](https://github.com/user-attachments/assets/ae5e3ead-87f9-4971-a7b3-6cacba715031)

  - Customers with lower recency (purchased recently) tend to have higher
monetary value.
  - The Champions and Loyal segments show this most clearly — they are clustered
in the lower-left corner, indicating both recent activity and high spending.
  - In contrast, Hibernating and Lost customers have high recency values
(purchased a long time ago) and low monetary scores.
  - This demonstrates a negative correlation between Recency and Monetary
value: the longer customers stay inactive, the less revenue they generate.

- **Bar Chart – Customer Count by Segment**
![Image](https://github.com/user-attachments/assets/08ecb637-4a1f-4daa-a39e-a17c58c6f52e)

  - Champions remain the single largest segment (highest count).
  - Hibernating customers and Lost customers together form a very large portion
of the base — each individually is comparable to (or larger than) Loyal and
Potential Loyalist segments.
  - Loyal and Potential Loyalist are meaningful but smaller than the combined
inactive groups, which indicates a sizeable retention risk if left unaddressed.

- **Total Rev | Average Rev | Proportion of Rev by Customer Segment**
![Image](https://github.com/user-attachments/assets/24663acf-cfae-4991-8816-5e508953c299)

![Image](https://github.com/user-attachments/assets/d2fa0b2a-47c8-4700-a7b3-dd212a1ba627)

![Image](https://github.com/user-attachments/assets/6129a80d-b9bb-4b9a-bc8e-83e0f1321eb9)

  - The company’s revenue heavily depends on Champions (61%) and Loyal (12%)
customers, emphasizing the need for strong retention strategies for these key
groups.
  - Revenue is highly concentrated in a few top-tier segments (Champions + Loyal),
which poses a dependency risk if these customers churn.
  - To reduce dependency, the business should also nurture Potential Loyalists and
New Customers into higher-value tiers through engagement, loyalty programs,
or tailored offers.
  - Cannot Lose Them, At Risk and Need Attention customers also show relatively
high average revenue, indicating that some once-high-value customers have
become inactive — should be prioritized for reactivation campaigns.

- **Line Chart - Revenue Trend Over Time**
![Image](https://github.com/user-attachments/assets/be4e27ed-1ae7-4085-a050-9276aff7e230)

  - The chart shows fluctuating revenue throughout the year, with several ups and
downs from 2010-12-01 to 2011-12-09.
  - The peak occurred in November 2011, reaching nearly 1 million dollars,
representing the highest monthly revenue during the observed period.
  - After the November 2011 peak, there was a sharp revenue drop in December
2011 (remain approximately 4.7 million dollars), decreasing by almost half
compared to the previous month.
  - Explanations for this December 2011 decline: Seasonality or Customer
Lifecycle Effects.

### 2. Non-UK Market
- **Proportion of UK vs Non-UK Revenue**
![Image](https://github.com/user-attachments/assets/fa361ce8-ed0c-4005-a686-5afa3170131c)

  - The business remains highly dependent on the UK market, with very limited
global penetration.

- **Top 10 Non-UK Countries Largest Revenue**
![Image](https://github.com/user-attachments/assets/d717907b-1835-46dc-ac07-84283d0ea1a0)

  - The company’s Non-UK revenue is heavily concentrated in Western Europe,
particularly in the Netherlands, EIRE, Germany, and France.
  - Expanding and investing in high-performing Non-UK countries (like the
Netherlands and EIRE) could significantly improve overall revenue stability.
  - There’s a clear growth opportunity in international markets, which could also
help reduce risk associated with over-reliance on the domestic (UK) market.

- **Customer Count by Segment**
![Image](https://github.com/user-attachments/assets/86dee2f6-711b-47b0-b0ce-cd0b867e7f17)

  - The At Risk segment has the highest number of customers (around 70), meaning
many Non-UK customers show declining engagement or purchase frequency.
  - The Non-UK market has a large proportion of customers at risk of churn,
indicating potential instability in customer retention.

- **Total Revenue by Customer Segment**
![Image](https://github.com/user-attachments/assets/827a55e1-bff7-46e5-9a0b-7cf35d921e84)

   - Champions contribute the highest total revenue by far (approximately
$700,000) and followed by Loyal (exceeding $250,000), highlighting the
importance of maintaining satisfaction and engagement for these key groups.
  - Retention should be the main priority, especially focusing on preventing high-
value at-risk customers from churning.

## III. Recommendations
- For the Marketing team of SuperStore, the most important indicator among the
three RFM metrics is Recency (R).
- While Frequency (F) and Monetary (M) provide valuable insights into customer
loyalty and spending power, Recency is the most actionable metric for
marketing — it helps prioritize timely, targeted communication to maximize
campaign effectiveness and prevent customer churn.
- Some recommendations for each segment customers group as below:

| **Segments** | **Characteristics** | **Recommendations** |
|-------------------------|---------------|---------------|
| **Active Customers** <br> • Champions <br> • Loyal <br> • Potential Loyalists | High purchase frequency and recency, strong engagement with the brand. | Maintain engagement through exclusive offers, early access, and personalized loyalty programs to retain their high-value contribution. |
| **At-Risk Customers** <br> • Need Attention <br> • About to Sleep <br> • At Risk | Declining purchase frequency and recency, showing early signs of disengagement. | Use targeted win-back campaigns, personalized discounts, and reminders to re-engage them before churn increases. |
| **Inactive Customers** <br> • Hibernating <br> • Lost Customers | Very low or no recent activity, likely churned. | Launch reactivation campaigns with strong incentives or gather feedback to understand why they left. |

