# Bangla Book Recommendation Dataset
## Summary
This repository contains the dataset and code for the paper [Towards Personalized Bangla Book Recommendation: A Large-Scale Multi-Entity Book Graph Dataset](https://arxiv.org/abs/2602.12129). In this work, we introduce a large-scale multi-entity heterogeneous graph dataset for Bangla book recommendation, integrating users, books, authors, publishers, and categories. Our framework enables the development of sophisticated graph-based recommendation systems. This contribution aims to enhance the discovery of Bangla literature through more accurate and personalized user experiences.

---

##  Models (Google Colab)

> Click any badge below to **open and run instantly** in Google Colab.  
> *(Dataset downloads automatically — no setup needed!)*

<br/>

| Model | Open in Colab | Model | Open in Colab |
|-------|:-------------:|-------|:-------------:|
| **Global Popularity** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/global_popularity_colab.ipynb) | **Category-Aware Popularity** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/category_aware_popularity_colab.ipynb) |
| **User-Based Collaborative Filtering** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/user_based_cf_colab.ipynb) | **Item-Based Collaborative Filtering** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/item_based_cf_colab.ipynb) |
| **Implicit Matrix Factorization (ALS)** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/implicit_mf_als_colab.ipynb) | **Explicit Matrix Factorization (SVD)** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/explicit_mf_svd_colab.ipynb) |
| **Two Tower Text Embedding** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/Two_Tower_Text_Embedding_colab.ipynb) | **LightGCN** | [![Colab](https://img.shields.io/badge/Open-Colab-F9AB00?style=flat-square&logo=googlecolab)](https://colab.research.google.com/github/backlashblitz/Bangla-Book-Recommendation-Dataset/blob/main/colabnotebooks/LightGCN_colab.ipynb) |

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
