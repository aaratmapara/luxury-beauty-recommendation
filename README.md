# Luxury Beauty Recommendation System
Recommendation system built on the **Amazon Luxury Beauty reviews dataset (~574k reviews, 12k products)**.  
Includes exploratory data analysis (EDA), baseline model, collaborative filtering (item & user), and matrix factorization (SVD) with evaluation metrics.

## Overview
The goal of this project is to recommend beauty products based on user review patterns.  
We start with a simple popularity baseline, then compare collaborative filtering and SVD to identify the most effective method.

## Dataset
- Source: Amazon Review Data (McAuley et al.) — [link](https://cseweb.ucsd.edu/~jmcauley/datasets.html#amazon_reviews)  
- Domain: Luxury Beauty  
- Size: ~574,000 reviews, 12,000 unique products  
- Columns: reviewerID, asin (product), rating, review text, votes, etc.

## Project Structure
- `Luxury Beauty Recommendation.ipynb` → Notebook with EDA, models, and evaluation  
- `requirements.txt` → Dependencies to reproduce results  
- `data/` → Dataset files (not pushed due to size)

## Models Used
- **Popularity Baseline** → ranks products by overall average rating  
- **Item-based Collaborative Filtering (CF)** → recommends products similar to those a user rated highly  
- **User-based Collaborative Filtering (CF)** → recommends based on similar users’ preferences  
- **Singular Value Decomposition (SVD)** → latent factor model capturing hidden product-user interactions  

## Results (Test Set, @5)
| Model              | Precision | Recall |
|--------------------|-----------|--------|
| Popularity Baseline | 0.046     | 0.090  |
| Item-based CF      | 0.064     | 0.153  |
| User-based CF      | 0.079     | 0.152  |
| SVD                | 0.074     | 0.187  |

**Conclusion:** Collaborative Filtering improves over the baseline, and SVD achieves the best recall, retrieving more relevant products per user.

## Reproducibility
All models were trained with `random_state=42` for consistent results.

## Limitations & Next Steps
- Data is limited to one Amazon category (Luxury Beauty).  
- Precision and recall remain modest; hyperparameter tuning and hybrid models could improve results.  
- Future work: try deep learning recommenders (e.g., neural collaborative filtering).

## References
- McAuley, J. et al. (2015). *Inferring Networks of Substitutable and Complementary Products*. KDD.  
- Pedregosa, F. et al. (2011). *Scikit-learn: Machine Learning in Python*. JMLR, 12, 2825–2830.  