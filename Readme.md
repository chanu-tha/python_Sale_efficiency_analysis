## Project Backgroud


Six weeks ago we launched a new line of office stationery. Despite the world becoming
increasingly digital, there is still demand for notebooks, pens and sticky notes.
Our focus has been on selling products to enable our customers to be more creative, focused
on tools for brainstorming. We have tested three different sales strategies for this, **targeted
email and phone calls, as well as combining the two**. We need to make sure we are using the best techniques to sell the new product effectively. The best approach may vary for each new product so we need to learn quickly what works and what doesn’t.

## Cleaning Process and Data Validation


The dataset contains 15000 rows and 8 columns before cleaning and validation. As I have validate all the columns against the criteria in the dataset table

- week: 6 unique values with no missing value, same as description since product had been launched 6 weeks ago. No cleaning needed
- sales_method: 5 unique values but it should have 3 unique values as per description. The column needs to be cleaned.
- customer_id: 15000 unique values, same as description. No cleaning is needed.
- nb_sold: numeric values, same as description, No cleaning is needed.
- revenue: numeric values with 1074 missing values. The column needs to be cleaned
- years_as_customer: numeric values but there are some values that are greater than company age. The column needs to be cleaned.
- nb_site_visits: numeric values
- state: 50 states which represent all states in US, same as the description. No cleaning is needed.

**Cleaning Process**

- week: The invalid values "email" and "em+call" were corrected to "Email" and "Email + Call," respectively. The column now contains three unique sales methods.
- years_as_customer: The company has operated for 41 years but there are some rows that exceed the company’s age. Therefore, rows with customer tenure exceeding this limit were corrected to 41 years, the company's age.
- revenue: This column has 1074 missing values, exceeding 5% of the total data. Since dropping these values could significantly impact further analysis, and revenue is crucial for identifying effective sales strategies, I imputed the missing values using the median revenue of nb_sold for each distinct sales method. This approach minimizes the impact on the distribution of revenue while reflecting the reality that nb_sold correlates with revenue and varies across different sales methods.

After validation, the dataset remains **15,000 rows and 8 columns** without missing values, and I decided to keep outliers as they may affect the performance of sales approaches.

## Executive Summary


- **Customer Distribution:** Email is the most widely used approach, reaching nearly half the customers, followed by Call and then the combined Email + Call approach. However, despite reaching fewer customers, Email + Call generates significantly more revenue than Call alone.
- **Revenue Trends:** While Email initially brought in the most revenue, it declined sharply over the six weeks. Email + Call showed the most consistent growth and ultimately generated the highest revenue per customer. This indicates that building relationships with customers over time leads to larger sales.
- **Recommended Approach:** Prioritize the Email + Call strategy. It delivers the highest revenue per customer (almost 4x more than Call alone) and demonstrates consistent growth. Use email to cast a wide net and generate initial interest, then follow up with calls to build relationships and close higher-value deals.
- **Performance Monitoring:** Track ****average revenue per customer on a weekly basis for each sales method. Compare this to a rolling average to quickly identify deviations and optimize performance. Consider also tracking "revenue per manhour" to assess the efficiency of time spent on each sales approach.

## Insightful Report


### How many customers were there for each approach?

![image.png]([attachment:5ab9c977-b12d-472f-a6e9-5b648dbc83f9:image.png](https://github.com/chanu-tha/images/blob/main/pen&brush_folder/Customer_contribution.png?raw=true))

Over the past six weeks, **Email** has been the dominant sales approach, reaching 7,466 customers (49.77%). **Call** follows with 4,962 customers (33.08%), while **Email + Call** has reached 2,572 customers (17.15%).

![image.png](attachment:dc381737-31be-4a35-906f-182b4dfc300c:image.png)

In terms of revenue contribution, **Email** remains the top performer with 725,439.82 USD (50.53%). However, **Email + Call**, despite reaching fewer customers, generated 473,838.05 USD (33.00%), indicating a higher revenue per customer compared to the **Call** approach, which generated 236,395.34 USD (16.47%).

### Spread of the Revenue

![image.png](attachment:8f5b3b77-868d-42df-92ad-ce5720d71c7c:image.png)

The overall revenue distribution is right-skewed with multiple spike nodes which can be caused by different distribution from different sale methods.

![image.png](attachment:76c1b24f-85e0-4011-918b-859a1ad629b1:image.png)

After categorizing each method by colors, distinct patterns revealed. The Call method appears to generate lower-value transactions, while the Email method seems to be associated with a broader range of revenue, including a significant proportion of mid-range transactions. Notably, the Email + Call method exhibits a concentration towards higher-value transactions, suggesting a potentially more effective strategy for securing larger deals.

![image.png](attachment:e9cd7ee1-12dc-488a-bf08-8e5248d4ced7:image.png)

Break down into each sale method

- Call: Revenue from "Call" is concentrated in the lower range, with a right-skewed distribution (average: $47.65, median: $49.27). This suggests a majority of transactions fall within a narrower revenue band.
- Email: The "Email" method shows a right-skewed distribution (average: $97.17, median: $95.79), indicating a larger proportion of lower-value transactions. However, it captures a wider range of revenue compared to "Call."
- Email + Call: This method exhibits a near-bell-shaped distribution (average: $184.23, median: $184.50), suggesting a more balanced spread across revenue levels. It also has the widest revenue spread among the three methods, indicating a greater diversity in transaction values.

### The difference in overtime revenue for each sale method

![image.png](attachment:049880b4-3971-416f-b64c-90d43265a9b1:image.png)

There are significant differences in revenue trends over time for each sales method. The first chart shows the total revenue generated by each sales method over six weeks. We see an overall downward trend in total revenue, possibly due to factors like initial launch excitement or seasonal variations.

Looking at individual methods, Email initially dominated, generating over $246,000 in the first week. However, its revenue declined significantly, reaching less than $25,000 by the end of the sixth week. Call revenue showed a gradual increase, starting at around $26,000 and peaking at over $55,000 in week five. Email + Call demonstrated the most consistent growth, starting with around $19,000 and surpassing both Email and Call to reach nearly $147,000 by week five.

The second chart reveals revenue per customer. Despite the overall revenue fluctuations, all methods experienced an increase in revenue per customer. Email + Call consistently outperformed the others, starting with $129 per customer and reaching $228 per customer by the end of the period ($99 increment). Email showed an increase from $87.50 to $131 per customer ($43.5 increment), while Call increased from $35 to $66 per customer ($31 increase).

![image.png](attachment:c350c153-bde4-46bb-bb17-557410770ae9:image.png)

A closer look at the scatter plot below reveals an intriguing dynamic. As the weeks progress after product launch, we observe a positive correlation between revenue per customer, the number of products sold, and the time elapsed. This suggests that building customer relationships and cultivating larger purchases often requires time. Factors such as customer consideration and approval processes may contribute to this observed trend.

**In conclusion**, there are significant differences in revenue trends over time for each sales method. While **Email** initially dominated in terms of total revenue, its performance declined significantly over time. In contrast, **"Email + Call"** showed consistent growth, surpassing other methods in both total revenue and revenue per customer. This suggests that **“Email + Call”** approach may be the most effective strategy for driving revenue and maximizing customer value.

Furthermore, our analysis reveals a positive correlation between revenue per customer and the time since product launch. This indicates that building strong customer relationships and cultivating larger purchases often takes time.

**Statistical Significance:**

It's important to note that the observed differences in revenue per customer between the sales methods are statistically significant. This indicates that these differences are not due to chance and strongly suggests that each sales method has a different level of success.

### Metric to monitor

To accurately assess the performance of each sales approach, we need a metric that accounts for differences in customer reach. Simply looking at total revenue can be misleading, as methods with a larger customer base will naturally generate higher revenue. Therefore, we recommend using average revenue per customer as our key metric. This metric provides a more equitable comparison by normalizing revenue against the number of customers reached, allowing us to evaluate the effectiveness of each approach in converting customers into revenue.

Based on the six-week data, we can establish an initial baseline for each sales method:

- **Email + Call:** $184.23
- **Email:** $97.17
- **Call:** $47.65

This baseline, established using the initial six weeks of data, provides a starting point for monitoring the performance of each sales approach. By tracking weekly average revenue per customer for each method, we can quickly identify any significant deviations from the **current** baseline. As more data accumulates, the baseline itself will be updated to reflect the evolving performance of each sales method

For example, after analyzing the initial six weeks of data, we found that "Email + Call" was the most efficient sales approach, generating the highest average revenue per customer. Based on this observation, we might consider reallocating resources, such as shifting manpower from the "Call" method, which had the lowest efficiency, towards the more promising "Email + Call" approach.

Moving forward, we would continue to monitor the weekly average revenue per customer for each method. We would compare the current week's average to the **rolling average** calculated from the previous weeks of data. This rolling average serves as our dynamic baseline, reflecting the evolving performance of each sales method.

If the current week's average for a particular method exceeds its rolling average, it indicates strong performance. Conversely, if it falls below the rolling average, it suggests a potential need for optimization, such as refining call scripts, improving email content, or reallocating resources.

### Recommendations

1. **Prioritize the "Email + Call" Approach:**
    - Our analysis reveals that the "Email + Call" approach consistently delivers the highest revenue return per customer. In fact, it generates four times more revenue per customer than the "Call" method and approximately two times more than the "Email" method. ****This indicates that this combined strategy is highly effective at generating significant revenue from each customer interaction. Focus team efforts on refining and expanding this approach to maximize revenue generation
2. **Optimize Email Strategy & Evaluate Call Method:**
    - Email remains a valuable tool for reaching a large audience with minimal effort. Utilize email campaigns to generate initial interest and build awareness, especially during product launches.
    - Monitor email campaign performance closely and adjust strategies based on weekly revenue.
    - Given that the Call method requires significant time investment per customer while generating the lowest average revenue per customer, carefully evaluate its continued use. Consider reallocating resources from "Call" to "Email" or "Email + Call" to maximize overall sales efficiency.
3. **Performance Monitoring:**
    - Continuously monitor weekly average revenue per customer for each sales method.
    - Compare this metric to a rolling average to identify efficiency and areas for improvement.
    - Use these insights to refine your sales approach, such as optimizing call scripts, enhancing email content, or reallocating resources to more effective channels.
4. **Focus on Building Customer Relationships:**
    - Our analysis suggests that customer value tends to increase over time. Invest in building strong customer relationships through personalized communication and exceptional service.
5. **Data Collection and Analysis:**
    - **Data Completeness:** Investigate the root cause of missing revenue values (NaN) and ensure data collection processes are robust and reliable.
    - **Time Tracking:** Track the time spent with each customer to develop a new metric: "Revenue per manhour." This will help you evaluate the efficiency of your sales efforts and identify areas for improvement.
    - **Product-Level Analysis:** Collect detailed product information (e.g., product ID, category) to analyze sales performance at the product level. This will enable you to identify top-selling products, tailor your sales approach to specific products, and identify opportunities for cross-selling and upselling.
