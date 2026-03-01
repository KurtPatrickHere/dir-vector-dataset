# dir-vector-dataset

This repository hosts two large-scale, real-world datasets — **WIKI-Dir** (derived from Wikipedia) and **ARXIV-Dir** (derived from arXiv). These datasets are specifically constructed to benchmark directory-semantic operations (such as DSQ and DSM) within vector databases. All associated data files are available for download via the Google Drive link provided below.

## Dataset Download

### Main Dataset Directory

Google Drive Shared Link: [htt](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[ps://](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[drive](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[.goog](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[le.co](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[m/dri](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[ve/fo](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[lders](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[/1T3z](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[9IDUb](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[Ibq0S](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[m3A-u](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[VGzUB](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[p1Q7R](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[CJgM?](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[usp=s](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[harin](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)[g](https://drive.google.com/drive/folders/1T3z9IDUbIbq0Sm3A-uVGzUBp1Q7RCJgM?usp=sharing)

Full access to both datasets for standardized, reproducible evaluation of DSQ (Directory-Semantic Query) and DSM (Directory-Semantic Maintenance) operations.

## Dataset Description

### 1. ARXIV-Dir (arXiv-based Dataset)

Built from 2.76M arXiv paper abstracts, featuring **two parallel hierarchies** (arXiv category taxonomy + temporal publication date structure). Supports evaluation of cross-hierarchy DSQ/DSM operations. Abstracts encoded into 1024D vectors (mxb-ai-embed-large-v1); includes 1,000 queries with directory constraints and brute-force ground truth.

#### File List & Purpose



| Filename                               | Description                                                                                   |
| -------------------------------------- | --------------------------------------------------------------------------------------------- |
| `arxiv_category_ground_truth.txt`      | Ground truth labels for category-based DSQ tasks, mapping queries to relevant paper IDs.      |
| `arxiv_category_query_constraint.json` | Directory constraints for category-specific queries (DSQ evaluation).                         |
| `arxiv_category_query_vectors.fvecs`   | 1024D vector embeddings for category-based queries (mxb-ai-embed-large-v1).                   |
| `arxiv_corpus_metadata.json`           | Metadata of arXiv papers (titles, authors, dates, abstracts, dual hierarchies).               |
| `arxiv_corpus_vectors.fvecs`           | 1024D vector embeddings of all 2.76M paper abstracts.                                         |
| `arxiv_ground_truth.txt`               | General DSQ ground truth labels (non-category-specific) for retrieval performance evaluation. |
| `arxiv_query_constraint.json`          | Directory constraints for general DSQ queries.                                                |
| `arxiv_query_vectors.fvecs`            | 1024D vector embeddings for general queries (aligned with corpus vectors).                    |

### 2. WIKI-Dir (DBpedia/Wikipedia-based Dataset)

Derived from Wikipedia/DBpedia, augmented with a **deep hierarchical structure** (363K unique directories, avg. depth 11.95) to simulate complex knowledge bases. Includes 1.94M items, 456 test queries, and 2k DSM (MOVE/MERGE) operations. Items encoded into 1024D vectors (bge-m3).

#### File List & Purpose



| Filename                              | Description                                                                                                   |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `dbpedia_dir_2m_corpus.jsonl`         | Core corpus of 1.94M DBpedia/Wikipedia entities with hierarchical directory annotations (JSON Lines format).  |
| `dbpedia_dir_2m_corpus_vectors.fvecs` | 1024D vector embeddings of the corpus (bge-m3) for DSQ similarity computation.                                |
| `dbpedia_dir_2m_corpus_paths.json`    | Hierarchical directory path information for corpus items (supports DSM operation testing).                    |
| `dbpedia_dir_2m_query.jsonl`          | 456 test queries with directory constraints (JSON Lines format) for DSQ evaluation.                           |
| `dbpedia_dir_2m_query_vectors.fvecs`  | 1024D vector embeddings for the query set (aligned with corpus vectors).                                      |
| `dbpedia_dir_2m_groundtruth.tsv`      | TSV-formatted ground truth labels, mapping queries to relevant entity IDs (for DSQ performance benchmarking). |

### Data Format Summary



* **Text/Metadata**: JSON, JSONL, TXT, TSV (UTF-8 encoded)

* **Vectors**: fvecs (1024-dimensional float vectors, compatible with `faiss`/`numpy`)

* **Core Use Case**: Benchmarking DSQ (Directory-Semantic Query) and DSM (Directory-Semantic Maintenance) operations in vector databases

## Disclaimer

This dataset is for **academic research and non-commercial use only**. Comply with arXiv, Wikipedia, and DBpedia copyright regulations. Unauthorized commercial use or distribution is prohibited.

