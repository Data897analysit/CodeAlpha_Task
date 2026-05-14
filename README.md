# CodeAlpha_Task

DataSet Link :- https://www.kaggle.com/datasets/grikomsn/amazon-cell-phones-reviews?utm_source=chatgpt.com

Project Overview

Analyzed smartphone customer reviews, ratings, prices, and sentiments to identify customer satisfaction patterns, brand performance, and business insights using Python and NLP techniques.

🎯 Business Problem

Brands often struggle to understand customer satisfaction, sentiment trends, and product performance from large review datasets. This project helps identify:

Customer sentiment patterns
Brand-wise performance
Price vs Rating relationship
Customer engagement trends 





PROBLEM STATEMENT

Although the dataset is structured, brands lack clear insights into customer satisfaction, rating patterns, sentiment distribution, and price–rating relationships. The challenge is to analyze ratings, reviews, and brand-wise performance to identify strengths, weaknesses, and improvement areas. Understanding customer sentiment is essential for making informed business and product decisions.

Task 1.
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

Used TextBlob polarity scores. Score > 0.1 → Positive Score < -0.1 → Negative Otherwise Neutral

7.6 Exploratory Data Analysis (EDA)

Performed:

Rating distribution

Price distribution

Brand-wise rating comparison

Monthly review trends

Helpful votes pattern

Task 2
7.7 Visualizations

Created charts:

Rating histogram

Trend wise rating and review

Brand-wise average rating, total review, average price bar chart

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

Overall, brands offering high performance at competitive pricing (Xiaomi, OnePlus) receive better ratings, while market leaders like Samsung rely on brand trust and wide availability.

8.3.Price vs Rating

Price does not strongly influence rating.

Both low-cost and high-cost phones can achieve high ratings. Customer satisfaction depends more on features, performance, brand trust, and user experience rather than price.

8.4Trend wise Rating and Total Reviews

Both rating & reviews rise sharply in December, indicating high customer satisfaction and high purchase volume.

The mid-year period (May–August) is also strong for reviews but shows mixed satisfaction (small rating dip).

Early-year (Jan–Apr) is the slowest period for both customer engagement and satisfaction.

8.5.Votes Rating wise

Helpful votes are highest for low-rated reviews, indicating customers trust critical feedback more.

This means customers pay more attention to critical or negative feedback when making purchase decisions. These reviews highlight key areas such as battery issues, device lag, camera quality concerns, or heating problems — making them highly valuable for both buyers and brands.

Task3
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

This project analyzed smartphone reviews using ratings, prices, sentiments, and brand-level patterns. Insights show that customer satisfaction does not depend on price—both budget and premium phones receive high ratings. Brands with higher review volume maintain stronger visibility. Sentiment analysis revealed that most reviews are positive, reflecting good market acceptance. Monthly trends indicate growing customer engagement. Overall, product quality, performance, and user experience drive customer satisfaction more than pricing or brand popularity. I want to write detail of this project in redme of GitHub can you rewrite according to jitna likhne ki jarurat hai jisse recruiter pad ker select ker sake ki ye project aacha hai

📱 Smartphone Review Sentiment Analysis & Customer Insights
📌 Project Overview
This project focuses on analyzing smartphone product reviews, ratings, pricing, and customer sentiments to identify customer satisfaction patterns and brand performance. The goal is to help businesses understand customer behavior, improve products, and make data-driven decisions using exploratory data analysis (EDA) and sentiment analysis techniques.

The project combines product-level and review-level datasets to uncover insights such as:

Customer satisfaction trends

Brand-wise performance comparison

Price vs Rating relationship

Sentiment distribution across brands

Monthly customer engagement trends

Helpful review behavior

🎯 Business Problem
Although the dataset is structured, brands often struggle to understand:

What customers truly think about their products

Which brands provide the best value for money

Whether price impacts customer satisfaction

Which months show higher customer engagement

What factors influence positive and negative reviews

This project solves these challenges by transforming raw review data into actionable business insights using Python, Pandas, and NLP techniques.

🛠️ Technologies Used
Python

Pandas

NumPy

Matplotlib

Seaborn

TextBlob

Jupyter Notebook

📂 Dataset Information
The project uses two datasets:

Items Dataset

Product details

Brand

Price

Product information

Reviews Dataset

Customer reviews

Ratings

Helpful votes

Review date

⚙️ Project Workflow
1️⃣ Data Loading
Imported datasets into Jupyter Notebook using Pandas.

import pandas as pd

items = pd.read_csv("items.csv")
reviews = pd.read_csv("reviews.csv")
2️⃣ Data Cleaning
Performed data preprocessing to improve data quality:

Checked missing values

Filled missing brand names using mode

Removed inconsistencies

Created dataset copy to preserve raw data

data = items.copy()
data['brand'].fillna(data['brand'].mode()[0], inplace=True)
3️⃣ Data Merging
Merged product and review datasets using ASIN.

data = pd.merge(items, reviews, on='asin', how='left')
4️⃣ Feature Engineering
Created a new column combining review title and body for better sentiment analysis.

data['full_review'] = data['title_x'] + " " + data['body']
5️⃣ Sentiment Analysis
Used TextBlob polarity scores to classify customer reviews into:

Positive

Neutral

Negative

Sentiment Rules
Score > 0.1 → Positive

Score < -0.1 → Negative

Otherwise → Neutral

from textblob import TextBlob

def sentiment_label(text):
    score = TextBlob(str(text)).sentiment.polarity
    
    if score > 0.1:
        return "Positive"
    elif score < -0.1:
        return "Negative"
    else:
        return "Neutral"
📊 Exploratory Data Analysis (EDA)
Performed detailed analysis on:

Rating distribution

Price distribution

Brand-wise ratings

Monthly review trends

Helpful votes analysis

Sentiment distribution

Price vs Rating relationship

📈 Visualizations Created
Rating Histogram

Price Distribution Plot

Brand-wise Average Rating

Brand-wise Total Reviews

Average Price Comparison

Sentiment Distribution

Monthly Review Trends

Helpful Votes Analysis

Price vs Rating Scatter Plot

🔍 Key Insights
⭐ Rating Distribution
Most customers gave ratings between 3.5 to 4 stars

Majority of users are satisfied with their smartphones

Very low proportion of extremely negative reviews

📱 Brand-wise Performance Analysis
Samsung
Highest number of reviews

Strong market presence and customer trust

Xiaomi
Best value-for-money brand

High ratings at affordable prices

OnePlus & Apple
Premium pricing with strong customer satisfaction

Lower review volume compared to Samsung

Nokia
Lower ratings despite budget pricing

Indicates feature or quality improvement opportunities

💰 Price vs Rating Analysis
Price does not strongly affect ratings

Both budget and premium smartphones receive high ratings

Customer satisfaction depends more on:

Performance

Camera quality

User experience

Brand trust

Battery life

📅 Monthly Trend Analysis
December shows highest reviews and ratings

Mid-year months (May–August) also show strong engagement

Early-year months have lower customer activity

This indicates seasonal buying behavior and promotion impact.

👍 Helpful Votes Analysis
Low-rated reviews receive the highest helpful votes

Customers trust critical feedback more while making purchase decisions

Negative reviews highlight important issues such as:

Battery problems

Heating issues

Camera quality concerns

Performance lag

😊 Sentiment Analysis Results
Positive sentiment dominates overall reviews

Negative reviews are relatively low

Samsung has the highest positive review volume

Brands with balanced pricing and performance receive better sentiments

💼 Business Recommendations
📌 Focus on Mid-Range Smartphones
Mid-range smartphones show:

Highest demand

Better ratings

Strong customer satisfaction

📌 Use Customer Feedback in Marketing
Promote features customers frequently praise:

Camera

Performance

Design

Battery life

📌 Improve After-Sales Service
Many negative reviews are related to:

Poor customer support

Service delays

Warranty issues

Improving service quality can increase customer trust.

📌 Launch Products During High Engagement Months
December and mid-year periods show:

Higher customer activity

More product engagement

Brands should target these periods for:

Promotions

Product launches

Marketing campaigns

📌 Conclusion
This project demonstrates how data analytics and NLP can help businesses understand customer satisfaction and market trends. The analysis reveals that customer satisfaction depends more on product quality and user experience than pricing alone.

Using sentiment analysis and exploratory data analysis, this project provides actionable insights that can help smartphone brands improve products, customer experience, and business strategy.

🚀 Future Improvements
Build a machine learning model for sentiment prediction

Deploy dashboard using Power BI or Streamlit

Add real-time review analysis

Perform aspect-based sentiment analysis

Create recommendation system

📷 Sample Dashboard & Visualizations
(Add your project screenshots here)

👩‍💻 Author
Priyanshi Rajput
Data Analyst | Business Analyst | Aspiring Business Consultant

Skills: SQL, Python, Power BI, Tableau, Excel

Interests: Data Analytics, NLP, Business Insights, Visualization


Mujhe is detail me se readme m kya add kerna hai sirf vahi do waki sab unnecessary detail hata do

📱 Smartphone Review Sentiment Analysis
📌 Project Overview
Analyzed smartphone customer reviews, ratings, prices, and sentiments to identify customer satisfaction patterns, brand performance, and business insights using Python and NLP techniques.

🎯 Business Problem
Brands often struggle to understand customer satisfaction, sentiment trends, and product performance from large review datasets. This project helps identify:

Customer sentiment patterns

Brand-wise performance

Price vs Rating relationship

Customer engagement trends

🛠️ Tech Stack
Python

Pandas

NumPy

Matplotlib

Seaborn

TextBlob

Jupyter Notebook

⚙️ Project Workflow
Data Cleaning & Preprocessing

Merged product and review datasets using ASIN

Performed Feature Engineering

Conducted Sentiment Analysis using TextBlob

Performed Exploratory Data Analysis (EDA)

Built visualizations for business insights

📊 Key Analysis Performed
Rating Distribution Analysis

Brand-wise Rating Comparison

Price vs Rating Analysis

Monthly Review Trend Analysis

Helpful Votes Analysis

Sentiment Distribution Analysis




PROBLEM STATEMENT

Although the dataset is structured, brands lack clear insights into customer satisfaction, rating patterns, sentiment distribution, and price–rating relationships. The challenge is to analyze ratings, reviews, and brand-wise performance to identify strengths, weaknesses, and improvement areas. Understanding customer sentiment is essential for making informed business and product decisions.

Task 1.
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

Used TextBlob polarity scores. Score > 0.1 → Positive Score < -0.1 → Negative Otherwise Neutral

7.6 Exploratory Data Analysis (EDA)

Performed:

Rating distribution

Price distribution

Brand-wise rating comparison

Monthly review trends

Helpful votes pattern

Task 2
7.7 Visualizations

Created charts:

Rating histogram

Trend wise rating and review

Brand-wise average rating, total review, average price bar chart

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

Overall, brands offering high performance at competitive pricing (Xiaomi, OnePlus) receive better ratings, while market leaders like Samsung rely on brand trust and wide availability.

8.3.Price vs Rating

Price does not strongly influence rating.

Both low-cost and high-cost phones can achieve high ratings. Customer satisfaction depends more on features, performance, brand trust, and user experience rather than price.

8.4Trend wise Rating and Total Reviews

Both rating & reviews rise sharply in December, indicating high customer satisfaction and high purchase volume.

The mid-year period (May–August) is also strong for reviews but shows mixed satisfaction (small rating dip).

Early-year (Jan–Apr) is the slowest period for both customer engagement and satisfaction.

8.5.Votes Rating wise

Helpful votes are highest for low-rated reviews, indicating customers trust critical feedback more.

This means customers pay more attention to critical or negative feedback when making purchase decisions. These reviews highlight key areas such as battery issues, device lag, camera quality concerns, or heating problems — making them highly valuable for both buyers and brands.

Task3
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

This project analyzed smartphone reviews using ratings, prices, sentiments, and brand-level patterns. Insights show that customer satisfaction does not depend on price—both budget and premium phones receive high ratings. Brands with higher review volume maintain stronger visibility. Sentiment analysis revealed that most reviews are positive, reflecting good market acceptance. Monthly trends indicate growing customer engagement. Overall, product quality, performance, and user experience drive customer satisfaction more than pricing or brand popularity. I want to write detail of this project in redme of GitHub can you rewrite according to jitna likhne ki jarurat hai jisse recruiter pad ker select ker sake ki ye project aacha hai

📱 Smartphone Review Sentiment Analysis & Customer Insights
📌 Project Overview
This project focuses on analyzing smartphone product reviews, ratings, pricing, and customer sentiments to identify customer satisfaction patterns and brand performance. The goal is to help businesses understand customer behavior, improve products, and make data-driven decisions using exploratory data analysis (EDA) and sentiment analysis techniques.

The project combines product-level and review-level datasets to uncover insights such as:

Customer satisfaction trends

Brand-wise performance comparison

Price vs Rating relationship

Sentiment distribution across brands

Monthly customer engagement trends

Helpful review behavior

🎯 Business Problem
Although the dataset is structured, brands often struggle to understand:

What customers truly think about their products

Which brands provide the best value for money

Whether price impacts customer satisfaction

Which months show higher customer engagement

What factors influence positive and negative reviews

This project solves these challenges by transforming raw review data into actionable business insights using Python, Pandas, and NLP techniques.

🛠️ Technologies Used
Python

Pandas

NumPy

Matplotlib

Seaborn

TextBlob

Jupyter Notebook

📂 Dataset Information
The project uses two datasets:

Items Dataset

Product details

Brand

Price

Product information

Reviews Dataset

Customer reviews

Ratings

Helpful votes

Review date

⚙️ Project Workflow
1️⃣ Data Loading
Imported datasets into Jupyter Notebook using Pandas.

import pandas as pd

items = pd.read_csv("items.csv")
reviews = pd.read_csv("reviews.csv")
2️⃣ Data Cleaning
Performed data preprocessing to improve data quality:

Checked missing values

Filled missing brand names using mode

Removed inconsistencies

Created dataset copy to preserve raw data

data = items.copy()
data['brand'].fillna(data['brand'].mode()[0], inplace=True)
3️⃣ Data Merging
Merged product and review datasets using ASIN.

data = pd.merge(items, reviews, on='asin', how='left')
4️⃣ Feature Engineering
Created a new column combining review title and body for better sentiment analysis.

data['full_review'] = data['title_x'] + " " + data['body']
5️⃣ Sentiment Analysis
Used TextBlob polarity scores to classify customer reviews into:

Positive

Neutral

Negative

Sentiment Rules
Score > 0.1 → Positive

Score < -0.1 → Negative

Otherwise → Neutral

from textblob import TextBlob

def sentiment_label(text):
    score = TextBlob(str(text)).sentiment.polarity
    
    if score > 0.1:
        return "Positive"
    elif score < -0.1:
        return "Negative"
    else:
        return "Neutral"
📊 Exploratory Data Analysis (EDA)
Performed detailed analysis on:

Rating distribution

Price distribution

Brand-wise ratings

Monthly review trends

Helpful votes analysis

Sentiment distribution

Price vs Rating relationship

📈 Visualizations Created
Rating Histogram

Price Distribution Plot

Brand-wise Average Rating

Brand-wise Total Reviews

Average Price Comparison

Sentiment Distribution

Monthly Review Trends

Helpful Votes Analysis

Price vs Rating Scatter Plot

🔍 Key Insights
⭐ Rating Distribution
Most customers gave ratings between 3.5 to 4 stars

Majority of users are satisfied with their smartphones

Very low proportion of extremely negative reviews

📱 Brand-wise Performance Analysis
Samsung
Highest number of reviews

Strong market presence and customer trust

Xiaomi
Best value-for-money brand

High ratings at affordable prices

OnePlus & Apple
Premium pricing with strong customer satisfaction

Lower review volume compared to Samsung

Nokia
Lower ratings despite budget pricing

Indicates feature or quality improvement opportunities

💰 Price vs Rating Analysis
Price does not strongly affect ratings

Both budget and premium smartphones receive high ratings

Customer satisfaction depends more on:

Performance

Camera quality

User experience

Brand trust

Battery life

📅 Monthly Trend Analysis
December shows highest reviews and ratings

Mid-year months (May–August) also show strong engagement

Early-year months have lower customer activity

This indicates seasonal buying behavior and promotion impact.

👍 Helpful Votes Analysis
Low-rated reviews receive the highest helpful votes

Customers trust critical feedback more while making purchase decisions

Negative reviews highlight important issues such as:

Battery problems

Heating issues

Camera quality concerns

Performance lag

😊 Sentiment Analysis Results
Positive sentiment dominates overall reviews

Negative reviews are relatively low

Samsung has the highest positive review volume

Brands with balanced pricing and performance receive better sentiments

💼 Business Recommendations
📌 Focus on Mid-Range Smartphones
Mid-range smartphones show:

Highest demand

Better ratings

Strong customer satisfaction

📌 Use Customer Feedback in Marketing
Promote features customers frequently praise:

Camera

Performance

Design

Battery life

📌 Improve After-Sales Service
Many negative reviews are related to:

Poor customer support

Service delays

Warranty issues

Improving service quality can increase customer trust.

📌 Launch Products During High Engagement Months
December and mid-year periods show:

Higher customer activity

More product engagement

Brands should target these periods for:

Promotions

Product launches

Marketing campaigns

📌 Conclusion
This project demonstrates how data analytics and NLP can help businesses understand customer satisfaction and market trends. The analysis reveals that customer satisfaction depends more on product quality and user experience than pricing alone.

Using sentiment analysis and exploratory data analysis, this project provides actionable insights that can help smartphone brands improve products, customer experience, and business strategy.

🚀 Future Improvements
Build a machine learning model for sentiment prediction

Deploy dashboard using Power BI or Streamlit

Add real-time review analysis

Perform aspect-based sentiment analysis

Create recommendation system

📷 Sample Dashboard & Visualizations
(Add your project screenshots here)

👩‍💻 Author
Priyanshi Rajput
Data Analyst | Business Analyst | Aspiring Business Consultant

Skills: SQL, Python, Power BI, Tableau, Excel

Interests: Data Analytics, NLP, Business Insights, Visualization


Mujhe is detail me se readme m kya add kerna hai sirf vahi do waki sab unnecessary detail hata do

📱 Smartphone Review Sentiment Analysis
📌 Project Overview
Analyzed smartphone customer reviews, ratings, prices, and sentiments to identify customer satisfaction patterns, brand performance, and business insights using Python and NLP techniques.

🎯 Business Problem
Brands often struggle to understand customer satisfaction, sentiment trends, and product performance from large review datasets. This project helps identify:

Customer sentiment patterns

Brand-wise performance

Price vs Rating relationship

Customer engagement trends

🛠️ Tech Stack
Python

Pandas

NumPy

Matplotlib

Seaborn

TextBlob

Jupyter Notebook

⚙️ Project Workflow
Data Cleaning & Preprocessing

Merged product and review datasets using ASIN

Performed Feature Engineering

Conducted Sentiment Analysis using TextBlob

Performed Exploratory Data Analysis (EDA)

Built visualizations for business insights

📊 Key Analysis Performed
Rating Distribution Analysis

Brand-wise Rating Comparison

Price vs Rating Analysis

Monthly Review Trend Analysis

Helpful Votes Analysis

Sentiment Distribution Analysis

📈 Visualizations
Rating Histogram

Brand-wise Average Rating

Brand-wise Total Reviews

Sentiment Distribution

Monthly Review Trends

Price vs Rating Scatter Plot

🔍 Key Insights
Most customers gave ratings between 3.5–4 stars

Samsung had the highest review volume and market presence

Xiaomi delivered the best value-for-money products

Price does not strongly impact customer ratings

Positive sentiment dominated overall customer reviews

Negative reviews received the highest helpful votes

💼 Business Recommendations
Focus more on mid-range smartphones

Improve after-sales service quality

Use positive customer feedback in marketing campaigns

Launch promotions during high-engagement months

Thanku 
Priyanshi 
Data Analyst 
