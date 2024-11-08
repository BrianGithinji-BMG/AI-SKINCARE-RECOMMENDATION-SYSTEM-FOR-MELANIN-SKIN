# AI-Powered-Recommendations-For-Melanin-Skin

![2d248f5507752726ddc2198b39071e4e](https://github.com/user-attachments/assets/9c7a2247-b758-4aee-8bc7-50fa0bf76f2d)

### Table of Contents

- [Business Overview](#business-overview)
- [Business Understanding](#business-understanding)
- [Data Understanding](#data-understanding)
- [Modeling and Evaluation](#modeling-and-evaluation)
- [Conclusion](#conclusion)
- [Repository Navigation](#repository-navigation)

## Business Overview

Our AI-powered recommendation system addresses the lack of tailored skincare solutions for individuals with melanin-rich skin. By leveraging two datasets on skin care products and products reviews by different users , our model delivers personalized skincare recommendations, achieving an accuracy of over 90% in predicting optimal products for various skin needs and on different budgets.

## Business Understanding

This project aims to develop a recommendation system using advanced AI techniques to cater specifically to Black women’s skincare needs. By integrating machine learning, content- based filtering, collaborative filtering, and sentiment analysis, the system will offer personalized skincare recommendations. Leveraging skin_tone (Author's skin tone (e.g. fair, tan, etc.) as a classification feature, we aim to distinguish and target products that align with melanin-rich skin concerns.

## Data Understanding

The dataset was collected via a Python scraper and contains:
- Product Information: Over 8,000 beauty products from the Sephora online store, including product and brand names, prices, ingredients, ratings, and various features. 
- User Reviews: Approximately 1 million reviews across over 2,000 products in the skincare category. These reviews include user appearances, skin types, and review ratings.

The key features include:
- Product Features: `product_id`, `product_name`, `brand_name`, `ingredients`, `rating`, `price_ksh`, `new`, `out_of_stock`, `highlights`. 
- Review Features: `author_id`, `rating`, `review_text`, `skin_type`, `skin_tone`, and
`helpfulness`.


### EDA

#### Count of Products by Skin Type
![download](https://github.com/user-attachments/assets/34553955-e5d2-4054-9135-39fb3e9f269d)


The distribution shows that products labeled for combination skin are the most common, followed by those for dry, normal, and then oily skin. This insight can guide product selection based on prevalent skin types and consumer demand within the Black women demographic.

#### Top 20 Recommended Products for Melanin Skin

![download](https://github.com/user-attachments/assets/8946f8fa-8448-4107-a84e-03e661bd4b6c)
The chart highlights skincare products tailored to the specific needs of melanated skin, focusing on hydration, hyperpigmentation, and sun protection. **Signature Moisturizer** leads with the highest recommendation count, emphasizing a strong demand for deep hydration. Products targeting dark spots, such as **Blue Algae Vitamin C Dark Spot Correcting Peel**, show the importance of tone-evening solutions, while sunscreens like **Mineral MatteSunscreen SPF 40 PA+++** address the need for effective sun protection without a white cast. This selection showcases a commitment to skincare that respects and meets the unique requirements of darker skin tones.

#### Out of stock Products and Recommendations based on skin tone

![download](https://github.com/user-attachments/assets/292c819f-04f0-44fa-b1c2-851bdb099e33)

Lighter skin tones show a higher count of both in-stock and out-of-stock products. This contrasts with deep skin tones which have fewer options overall and lower in-stock counts. This discrepancy might indicate a supply gap for these deeper skin tones, which are more likely to face limited product availability.

Products targeting melanated skin tones receive fewer recommendations, suggesting that product options may not fully address the needs or preferences of these individuals.

#### Heatmap of Product Count by Skin Tone Category and Skin Type
![download](https://github.com/user-attachments/assets/85e65e5a-60de-4f85-8d36-bbc1aa258743)

The heatmap analysis of `skin_type` and `skin_tone_category` highlights important insights that align closely with our objective of providing tailored skincare recommendations for Black women. Our data reveals a concentration of products available for combination and dry skin types, particularly within lighter skin tones. However, there is a notable scarcity of options for deeper skin tones, suggesting that Black women may have fewer product options specifically suited to their needs. This gap underscores the limited market focus on skincare for melanin-rich skin concerns, such as hyperpigmentation, dryness, and sensitivity, which are often more pronounced in deeper skin tones.

These findings directly support our business problem: many existing recommendation systems fail to provide targeted solutions for Black women. The evident lack of specialized options for drier skin in deeper tones emphasizes an opportunity to develop and recommend products that address this unique need. By prioritizing these underserved areas, our recommendation system can significantly enhance satisfaction and efficacy for Black women seeking products that work for their melanin-rich skin.





## Modeling Approach
1. Collaborative Filtering (SVD)
- Description: Uses matrix factorization to predict user-product interactions based on historical data.
- Implementation: Leveraged scikit-surprise for efficient matrix decomposition.
- Limitations: Struggles with new users/products (cold start problem).
  
2. Content-Based Filtering
- Description: Recommends products by analyzing attributes like ingredients, highlights, and price_tier.
- Implementation: Applied TF-IDF vectorization with sklearn for feature extraction, followed by cosine similarity to assess relevance.
- User Profile Integration: Included user attributes (e.g., skin_type, eye_color) for a personalized touch.
  
3. K-Nearest Neighbors (KNN)
- Description: A similarity-based approach that identifies similar users or products based on features.
- Implementation: Used KNN to find the most similar products based on features and recommend them to users.
- Application: Enhanced recommendations in the absence of significant user interaction data (mitigates cold start problem).

4. Sentiment Analysis
- Description: Analyzes user reviews to determine sentiment polarity (positive, neutral, negative) and integrates this with product recommendations.
- Implementation: Used TextBlob to assess review sentiment, categorizing products based on user satisfaction.
- Integration: Products with positive sentiment are prioritized in recommendations to increase user satisfaction.
  ![download](https://github.com/user-attachments/assets/0e5aa440-f8d6-4c6b-bf44-8a4a890304b5)

5. Hybrid Model
- Description: Combines predictions from both collaborative and content-based models using a weighted average.
- Parameter Tuning: Optimized alpha to balance contributions of each model.

## Evaluation
RMSE: Used as the main metric to gauge prediction accuracy.
Results: Hybrid model outperformed standalone models, particularly effective with users who had historical data and defined product preferences.


## Conclusion
- The project successfully developed a skincare recommendation system that addresses a key need for individuals with melanin-rich skin: finding skincare products tailored to their unique needs. Through a combination of content-based and collaborative filtering methods, along with sentiment analysis, the system provides personalized and effective product suggestions, making it easier for users to discover products suited to their specific skin concerns.

- Key accomplishments include the effective implementation of content-based filtering using ingredient similarity and collaborative filtering with SVD to capture user-product interactions. Additionally, the sentiment analysis model enhances the recommendation system by prioritizing products with positive reviews, ensuring higher relevance and user satisfaction. The Streamlit interface further supports a seamless user experience, allowing easy access to personalized recommendations.

- This project underscores the potential of AI-driven solutions in meeting specific market demands and demonstrates how data-driven approaches can enhance inclusivity in the skincare industry. Future improvements could include expanding the dataset to cover a wider range of brands and user profiles, optimizing the hybrid recommendation model, and incorporating real-time feedback to continuously improve recommendation accuracy. Overall, this project paves the way for a more personalized and inclusive approach to skincare, ultimately empowering individuals with tailored product recommendations that cater to their distinct needs.

## Recommendations

- **Enhance User Engagement:** Incorporate user feedback mechanisms to continually refine the recommendation algorithms and improve user satisfaction.
- **Expand Dataset Diversity:** Increase the dataset size and diversity to cover a broader range of products and user experiences, ensuring a more comprehensive recommendation system.
- **Implement Educational Resources:** Include educational content about skincare for melanin-rich skin, helping users understand their specific skincare needs and product ingredients.
- **User Interface Improvements:** Focus on optimizing the user interface for ease of use, ensuring that users can quickly find and receive tailored recommendations.
- **Collaborate with Skincare Experts:** Partner with dermatologists and skincare specialists to validate product recommendations and ensure they meet the specific needs of users with melanin-rich skin.


