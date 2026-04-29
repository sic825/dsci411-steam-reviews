# DSCI 411 — Steam Reviews NLP Classification

End-of-semester project for DSCI 411 (Data Management for Big Data) at Lehigh University, Spring 2026.

## Team
- Simon Chen (sic825)
- Thoi Quach (thq225)

## Research Question
Can NLP-derived text features from Steam user reviews predict whether a player recommends a game? How does classifier performance compare between English and Simplified Chinese reviews?

## Data
[Steam Reviews 2021](https://www.kaggle.com/datasets/najzeko/steam-reviews-2021) — ~21M reviews across ~300 games, 8GB CSV.

## Pipeline
1. Ingest CSV → HDFS on the Lehigh Limulus cluster
2. Convert to Parquet (Snappy-compressed, columnar) for query speed
3. Tokenize, vectorize (TF-IDF), classify (Logistic Regression, Random Forest)
4. Train per-language models and compare

## Stack
PySpark (MLlib), HDFS, Zeppelin, jieba (for Schinese tokenization)

## Repo Structure
- `notebooks/zeppelin/` — Zeppelin .zpln exports run on the cluster
- `notebooks/local/` — Jupyter notebooks for local development on samples
- `scripts/` — utility scripts (data download, preprocessing helpers)
- `docs/` — final report, methodology notes
- `slides/` — presentation slides