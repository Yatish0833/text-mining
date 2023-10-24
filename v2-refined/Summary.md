## Summary: `v2-refined`

The `v2-refined` directory is a systematic compilation of Jupyter notebooks, each detailing distinct phases of the project. Here's a brief description of its contents:

- **Part1-data_retrival.ipynb**: Outlines the primary steps of data retrieval, focusing on fetching relevant genetic data.
  
- **Part2-filter_data.ipynb**: Focuses on refining the fetched data, ensuring its quality and relevance.

- **Part3-abstracts_retrival.ipynb**: Handles the extraction of pertinent abstracts, which form the primary dataset for subsequent text mining tasks.

- **Part4-filter_abstracts.ipynb**: Aims at filtering the acquired abstracts to ensure their relevance and coherence.

- **Part5-sentence_extraction.ipynb**: Breaks down abstracts into individual sentences, prepping them for mining algorithms.

- **Part6-01-kmeans_approach.ipynb**: Embarks on the first approach using KMeans clustering, clustering sentences based on their semantic significance.

- **part6a-02-approach2-BERTtrain.ipynb**: Leverages BERT for the project's second approach, fine-tuning it on the sentence dataset.

- **part6b-02-MLM_approach.ipynb**: Builds upon the BERT approach, employing a Masked Language Modeling (MLM) variant for enhanced extraction capabilities.

- **result-data-files.zip**: A zipped folder housing the final results, showcasing the extracted genetic interactions in a structured manner.

- The intermediatie data files & trained model files due to size constraints are hosted on Figshare. Access:  http://bit.ly/46L3Pzi

The `v2-refined` directory exemplifies the methodological approach adopted throughout the project. 
Each notebook, complemented with descriptive commentary and a logical flow, ensures clarity, reproducibility, and scalability.
