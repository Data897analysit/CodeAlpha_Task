# CodeAlpha_Task

DataSet Link :- https://www.kaggle.com/datasets/grikomsn/amazon-cell-phones-reviews?utm_source=chatgpt.com

.PROBLEM STATEMENT
Although the dataset is structured, brands lack clear insights into customer satisfaction, rating patterns, sentiment distribution, and price–rating relationships. The challenge is to analyze ratings, reviews, and brand-wise performance to identify strengths, weaknesses, and improvement areas. Understanding customer sentiment is essential for making informed business and product decisions.


# Task 1.

7.1 Data Loading

Both tables are imported into Jupyter Notebook using Pandas.

7.2 Data Cleaning

Checked missing values

Filled brand nulls using mode

Created a copy of the dataset to avoid modifying raw data

7.3 Data Merging

Left join on ASIN to combine product and review data.

data = pd.merge(items, reviews, on='asin', how='left')

7.4 Feature Engineering

Created full_review column combining title and body.

data['full_review'] = data['title_x'] + " " + data['body']

7.5 Sentiment Analysis

Used TextBlob polarity scores.
Score > 0.1 → Positive
Score < -0.1 → Negative
Otherwise Neutral

7.6 Exploratory Data Analysis (EDA)

Performed:

Rating distribution

Price distribution

Brand-wise rating comparison

Monthly review trends

Helpful votes pattern

#  Task 2

7.7 Visualizations

Created charts:

Rating histogram

Trend wise rating and review

Brand-wise average rating, total review, average price  bar chart

Brand wise Sentiment distribution

Sentiment Distribution

8.Analysis & Insights

8.1 Rating Distribution

The most common rating people gave this phone was 3.5 stars. A lot of people were pretty happy too, giving 4 stars. It seems most customers feel just okay to good .

8.2.Brand wise Average Rating , Total Reviews, Average Price 

Samsung leads the market with the highest number of customer reviews, indicating strong sales and brand presence.

Xiaomi provides the best customer satisfaction at the lowest price, making it the top value brand.

OnePlus and Apple are premium brands with high prices and strong ratings but limited customer volume.

Nokia shows low ratings even at low prices, suggesting quality or feature issues.

Overall, brands offering high performance at competitive pricing (Xiaomi, OnePlus) receive better ratings, while market leaders like Samsung rely on brand trust and wide 
availability.

8.3.Price vs Rating

Price does not strongly influence rating.

 Both low-cost and high-cost phones can achieve high ratings. Customer satisfaction depends more on features, performance, brand trust, and user experience rather than 
 price.
 
8.4Trend wise Rating and Total Reviews

Both rating & reviews rise sharply in December, indicating high customer satisfaction and high purchase volume.

The mid-year period (May–August) is also strong for reviews but shows mixed satisfaction (small rating dip).

Early-year (Jan–Apr) is the slowest period for both customer engagement and satisfaction.

8.5.Votes Rating wise 

Helpful votes are highest for low-rated reviews, indicating customers trust critical feedback more.

 This means customers pay more attention to critical or negative feedback when making purchase decisions. These reviews highlight key areas such as battery issues, device lag, camera quality concerns, or heating problems — making them highly valuable for both buyers and brands.

# Task3

9.Sentiment Analysis 

Positive sentiment dominates overall, reflecting strong customer satisfaction across brands.

Negative sentiment is relatively small but concentrated in certain brands, highlighting areas for improvement.

Samsung shows the largest number of positive reviews, reinforcing its market trust and widespread adoption.


10.Business Recommendations

Mid-range phones get the best ratings and highest demand. Launch more models in this price segment.

If customers praise camera, performance, or design, brands should use these strengths in ads to attract buyers.

Many negative reviews come from poor after-sales service. Better service will reduce complaints and increase trust.

Months with high review activity show high customer interest. Brands should use these months for promotions or new launches.


Conclusion 

This project analyzed smartphone reviews using ratings, prices, sentiments, and brand-level patterns. Insights show that customer satisfaction does not depend on price—both budget and premium phones receive high ratings. Brands with higher review volume maintain stronger visibility. Sentiment analysis revealed that most reviews are positive, reflecting good market acceptance. Monthly trends indicate growing customer engagement. Overall, product quality, performance, and user experience drive customer satisfaction more than pricing or brand popularity.

Thank You
