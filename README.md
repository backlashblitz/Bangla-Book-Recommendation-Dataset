# Bangla Book Recommendation Dataset
## Summary
This repository contains the dataset and code for the paper [Towards Personalized Bangla Book Recommendation: A Large-Scale Multi-Entity Book Graph Dataset](https://arxiv.org/abs/2602.12129). In this work, we introduce a large-scale multi-entity heterogeneous graph dataset for Bangla book recommendation, integrating users, books, authors, publishers, and categories. Our framework enables the development of sophisticated graph-based recommendation systems. This contribution aims to enhance the discovery of Bangla literature through more accurate and personalized user experiences.

---

## 🚀 Baseline Models (Google Colab)

Click any model name below to download the Colab notebook and run it instantly — dataset is downloaded automatically.

| Model | Open in Colab |
|---|---|
| Global Popularity | [📓 Download Notebook](colabnotebooks/global_popularity_colab.ipynb) |
| Category-Aware Popularity | [📓 Download Notebook](colabnotebooks/category_aware_popularity_colab.ipynb) |
| User-Based Collaborative Filtering | [📓 Download Notebook](colabnotebooks/user_based_cf_colab.ipynb) |
| Item-Based Collaborative Filtering | [📓 Download Notebook](colabnotebooks/item_based_cf_colab.ipynb) |
| Implicit Matrix Factorization (ALS) | [📓 Download Notebook](colabnotebooks/implicit_mf_als_colab.ipynb) |
| Explicit Matrix Factorization (SVD) | [📓 Download Notebook](colabnotebooks/explicit_mf_svd_colab.ipynb) |

> **Note:** The SVD notebook requires a one-time kernel restart after the first cell runs (due to a NumPy version fix). All other notebooks run with a single **Runtime → Run all**.

---

## Citation
If you use the code, dataset or model checkpoints, please cite the following work:
```bibtex
@misc{ahmed2026personalizedbanglabookrecommendation,
      title={Towards Personalized Bangla Book Recommendation: A Large-Scale Multi-Entity Book Graph Dataset}, 
      author={Rahin Arefin Ahmed and Md. Anik Chowdhury and Sakil Ahmed Sheikh Reza and Devnil Bhattacharjee and Muhammad Abdullah Adnan and Nafis Sadeq},
      year={2026},
      eprint={2602.12129},
      archivePrefix={arXiv},
      primaryClass={cs.IR},
      url={https://arxiv.org/abs/2602.12129}, 
}
```
