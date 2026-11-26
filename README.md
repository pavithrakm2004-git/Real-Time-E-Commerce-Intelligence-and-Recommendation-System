# Real-Time E-Commerce Intelligence and Recommendation System

### Using Apache Spark and Cloud Computing

A Big Data capstone project that builds a real-time e-commerce recommendation system using Apache Spark, PySpark, Machine Learning, and Structured Streaming.

## Project Overview

E-commerce platforms generate millions of customer interactions, including product views, cart additions, and purchases. Traditional batch-based recommendation systems cannot always respond quickly to changing customer interests.

This project develops an end-to-end recommendation system that processes historical and live customer interactions to generate personalized recommendations, identify similar products, and discover trending products in real time.

## Team Members

- **Pavithra K M**
- **Asna Abbas**

**Institution:** School of Digital Science, Digital University Kerala  
**Project:** Big Data and Cloud Technology  
**Date:** November 2026

## Technologies Used

- Python
- Apache Spark
- PySpark
- Spark SQL
- Spark MLlib
- ALS (Alternating Least Squares)
- MinHash and Locality-Sensitive Hashing (LSH)
- Spark Structured Streaming
- FastAPI
- Docker
- Pandas
- NumPy
- Matplotlib
- Parquet

## System Architecture

The system follows a three-layer architecture:

1. **Batch Layer**
   - Historical data processing.
   - Data cleaning and transformation.
   - ALS collaborative filtering.
   - Product similarity using MinHash and LSH.

2. **Speed Layer**
   - Real-time event processing using Spark Structured Streaming.
   - Sliding-window analysis.
   - Trending products and categories.
   - Recent customer interests.

3. **Serving Layer**
   - Hybrid recommendation engine.
   - REST API using FastAPI.
   - Combines historical recommendations with real-time trends.

## Dataset

The project uses the **REES46 E-Commerce Behavior Dataset**, containing real customer interactions from an online multi-category store.

Dataset features include:

- Event time
- Event type
- Product ID
- Category
- Brand
- Price
- User ID
- User session

The project uses a 5% sample of the October 2019 dataset, containing approximately 2.1 million interactions.

Since the dataset does not provide explicit ratings, implicit ratings are derived from customer behaviour:

| Interaction | Rating |
|---|---:|
| Product View | 1 |
| Add to Cart | 3 |
| Purchase | 5 |

Product descriptions are constructed using category, brand, and price information for similarity analysis.

## Key Features

- Large-scale data processing using Apache Spark.
- Data cleaning and exploratory data analysis.
- Spark SQL-based business analytics.
- RDD and DataFrame performance comparison.
- Product similarity using Shingling, MinHash, and LSH.
- Personalized recommendations using ALS.
- Hybrid recommendation combining ALS, content similarity, and trends.
- Real-time event processing using Structured Streaming.
- REST API development using FastAPI.
- Dashboard-based visualization of trends and customer activity.

## Results and Performance

The experiments produced the following results:

| Experiment | Result |
|---|---:|
| Total cleaned interactions | 2,117,673 |
| Unique users | 967,811 |
| Unique products | 105,497 |
| Unique sessions | 1,650,476 |
| DataFrame aggregation time | 0.21 seconds |
| RDD aggregation time | 3.42 seconds |
| MinHash error (256 hash functions) | 0.014 |
| Streaming micro-batch processing time | 501 ms |
| Streaming throughput | ~3,140 rows/sec |
| Average API response time | 2.55 ms |

The hybrid recommendation approach improved Precision@10 by approximately 39% compared with ALS alone.

The experiments also showed that popularity-based recommendations performed slightly better than personalized models on the sampled test dataset. This highlights the challenges of data sparsity, popularity imbalance, and cold-start problems.

## Project Structure

```text
Real-Time-Ecommerce-Recommendation-System/
│
├── CODE.ipynb
├── Report.pdf
├── README.md
├── requirements.txt
│
└── images/
    ├── architecture.png
    ├── dashboard.png
    ├── results.png
    └── 24 additional report figures
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/pavithrakm2004-git/Real-Time-E-Commerce-Intelligence-and-Recommendation-System.git
```

### 2. Navigate to the Project

```bash
cd Real-Time-Ecommerce-Recommendation-System
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure Java

Install Java 11 or Java 17 and configure `JAVA_HOME` before running Spark.

### 6. Run the Jupyter Notebook

```bash
jupyter notebook CODE.ipynb
```

Run the notebook cells sequentially.

The notebook downloads the required REES46 October 2019 dataset if it is not already available.

**Note:** The dataset is large. The notebook uses a 5% sample by default to make experimentation faster. Running the full dataset requires more storage and computing resources.

## API Endpoints

The recommendation service provides the following endpoints:

- `/recommend` – Product recommendations.
- `/similar` – Similar product search.
- `/trending` – Trending products.
- `/health` – API health check.

## Future Enhancements

- Deploy the system on a cloud platform.
- Improve personalized recommendation accuracy.
- Enhance cold-start handling.
- Integrate additional customer behaviour signals.
- Scale streaming processing across a distributed cluster.

## References

- REES46 E-Commerce Behavior Dataset.
- Apache Spark Documentation: https://spark.apache.org/docs/latest/
- PySpark Documentation: https://spark.apache.org/docs/latest/api/python/
- FastAPI Documentation: https://fastapi.tiangolo.com/

---

**Developed by Pavithra K M and Asna Abbas**  
School of Digital Science, Digital University Kerala.
