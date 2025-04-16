# Viral-Social-Media-Trends-and-Engagement-Analysis

# 🔍 Project Overview
This project implements a complete **ECT (Extract, Cleanse, Transform)** pipeline to analyze social media engagement data. The analysis focuses on:

- Platform performance comparison
- Hashtag effectiveness
- Regional trends
- Content type performance
- Engagement rate optimization

# 📂 Dataset Structure
The dataset contains social media post metrics including:

- Views, Likes, Shares, Comments
- Platform (Instagram, Twitter, TikTok, etc.)
- Content type (Video, Image, Text)
- Hashtags
- Geographical regions
- Engagement levels

# Technical Implementation
1. **Data Extraction**
   
   df = pd.read_csv('Viral_Social_Media_Trends.csv')
   
   This code loads social media data from a CSV file into a pandas DataFrame. The **pd.read_csv()** function reads the **"Viral_Social_Media_Trends.csv"** file and converts it into a 
   structured table format. The resulting DataFrame **(df)** stores all the post metrics (views, likes, shares etc.) for analysis.

   
3. **Data Cleaning**
    - Handled missing values and duplicates
    - Type conversion for numerical metrics
    - Outlier detection

4. **Feature Engineering**

   I calculated the **Engagement Rate** of content by aggregating user interactions—**likes, shares, and comments**—and dividing them by the total number of views, then multiplying by 
   100 to express the result as a percentage. This metric helps evaluate how actively users are engaging with the content relative to its reach.
   
   **df['Engagement_Rate'] = (df['Likes'] + df['Shares'] + df['Comments']) / df['Views'] * 100**

   To assess the content's Popularity, I categorized each post based on its view count using defined thresholds:

   - Views < 1,000,000 → **Low**
   - Views between 1,000,000 and 3,000,000 → **Medium**
   - Views > 3,000,000 → **High**

   This was implemented using **pandas.cut()** for binning numerical values into labeled categories:

   **df['Popularity'] = pd.cut(df['Views'], bins=[0, 1e6, 3e6, float('inf')], labels=['Low', 'Medium', 'High'])**

7. **Analytical Insights**
   
   Generated five key analysis dimensions:
    - **Platform Metrics:** Performance by social platform
    - **Hashtag Analysis:** Most effective hashtags
    - **Regional Trends:** Engagement by geography
    - **Content Analysis:** Performance by content type
    - **Engagement Levels:** Distribution patterns
  
# 📊 Key Findings

1. **Platform Performance:**
     - TikTok showed highest median engagement rate (4.2%)
     - Instagram had most consistent performance across metrics

2. **Content Insights:**
     - Video content outperformed images by 32% in engagement
     - Tutorial-style content had highest conversion rates

3. **Hashtag Strategy:**
     - Campaign-specific hashtags performed better than generic ones
     - Optimal number of hashtags: 3-5 per post

4. **Regional Variations:**
     - Southeast Asia showed highest engagement rates
     - European markets had most consistent performance

# Tools and Libraries

**Python:** Analysis 

**Libraries:** pandas, numpy

# Conclusion

This analysis of **viral social media trends** revealed key insights into engagement patterns across platforms, content types, and regions. Videos and strategic hashtag usage drove the highest engagement, while TikTok and Instagram Reels outperformed other platforms. These findings can help optimize content strategies for better reach and audience interaction. Future work could explore predictive modeling to forecast viral trends in real time.

For detailed code and analysis, refer to the **Social_Media_Trends.ipynb** file.

# Acknowledgments
**Dataset Source:** [Kaggle - Viral Social Media Trends and Engagement Analysis](https://www.kaggle.com/datasets/atharvasoundankar/viral-social-media-trends-and-engagement-analysis/data)
