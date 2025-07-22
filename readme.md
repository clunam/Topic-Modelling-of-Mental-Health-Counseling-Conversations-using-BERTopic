# Topic Modelling of Mental Health Counseling Conversations using BERTopicr

## Collaborators
- [Dr. Agus Budi Raharjo, S.Kom, M.Kom., Ph.D.](https://www.its.ac.id/informatika/id/profil-agus-budi-raharjo/)  
- [Prof. Dr. Diana Purwitasari, S.Kom, M.Sc.](https://www.its.ac.id/informatika/profil-diana-purwitasari/)

## Executive Summary
Mental health is an urgent global concern, with depression and anxiety rising sharply after the COVID-19 pandemic.  
As demand for psychological support grows, **online text-based counseling** has become increasingly popular for its accessibility and anonymity.  

This project applies **BERTopic**, a transformer-based topic-modelling technique, to uncover key psychological themes in counseling conversations.  
Compared with traditional LDA methods, BERTopic produces **more semantically coherent and human-interpretable topics**, offering actionable insights for digital mental-health platforms.


## Background
- Global pandemic triggered **~27% rise in major depression** and **~25% rise in anxiety disorders** worldwide (Santomauro et al., 2021).  
- In Indonesia, about **15 million adolescents** reported mental-health issues in 2023, and over **50% of adults** experienced severe post-pandemic stress.  
- Online text-based counseling (e.g., Ibunda.id, Bicarakan.id) is growing rapidly; the **global online-therapy market** is projected to grow from **USD 3.8B in 2024** to **over USD 10B by 2031**.  

These counseling conversations are **large-scale, unstructured, and emotionally nuanced**, making traditional topic-modelling methods like **LDA** less effective.  
**BERTopic** leverages transformer embeddings with UMAP + HDBSCAN clustering and c-TF-IDF to capture nuanced, emotionally rich themes.


## Goals
- Extract and interpret key psychological themes from counseling conversation transcripts.
- Compare preprocessing strategies (lemmatization active vs inactive) and measure their impact on topic quality.
- Evaluate topic coherence, diversity, and cluster stability.


## Deliverables
- **Cleaned & preprocessed dataset** of counseling conversations.  
- **BERTopic model notebook** with reproducible code.  
- **Visualizations**: topic hierarchy, inter-topic distance map, and representative keywords.  
- **Evaluation report** comparing preprocessing strategies and metrics.  
- **Key insights** for mental-health service providers.

## Data Description
- **Source**: CounselChat.com mental-health Q&A dataset (Kaggle 2022).
- **Format**: CSV (each row = one conversation transcript).  
- **Focus**: questionText column only
- Data anonymized; no personal identifiers retained.

### Dataset Size  

- **Before Cleaning**  
  - 20200325_counsel_chat.csv → 2,129 entries (avg. 53.6 words)  
  - counselchat-data.csv → 1,383 entries (avg. 57.6 words)  
  - Combined → **3,512 entries** (avg. 55.2 words)  

- **After Cleaning**  
  - 20200325_counsel_chat.csv → 828 entries (avg. 64.1 words)  
  - counselchat-data.csv → 718 entries (avg. 64.9 words)  
  - Combined → **994 unique entries** (avg. 69.5 words)  


## Methodology

![Methodology Overview](/src/img/01.png)

1. **Preprocessing**  
Text cleaning, stopword removal, optional lemmatization.  

2. **Semantic Embedding**  
`SentenceTransformers` to create contextual document embeddings.  

3. **Dimensionality Reduction**  
`UMAP` to project high-dimensional embeddings into a low-dimensional space.  

4. **Clustering**  
`HDBSCAN` to detect dense clusters of semantically similar documents.  

5. **Topic Extraction**  
`c-TF-IDF` to generate representative keywords per cluster.  

6. **Evaluation**  
   - Quantitative: coherence (c_V, NPMI), topic diversity, outlier ratio.  
   - Qualitative: manual review and semantic validation.


## Results & Insights
- **Active lemmatization** produced **22 topics** with even distribution.  
- **Non-lemmatization** produced **14 topics**, with one dominant cluster (328 documents) but higher technical stability.  
- LDA baseline achieved highest c_V (0.52) but yielded overly general topics lacking psychological depth.  
- BERTopic captured **emotionally nuanced themes** that traditional LDA could not.

**Business Implication:**  
BERTopic’s semantically coherent topics can guide platform providers in tailoring content, detecting emerging mental-health concerns, and prioritizing counselor resources.


## Limitations & Next Steps
- Only text data analyzed; no multimodal signals (e.g., voice, video).  
- Future work: real-time monitoring of live counseling chats, domain-specific embedding fine-tuning.


## References
- Santomauro et al., 2021  
- Wahdi et al., 2023  
- Nugroho et al., 2023  
- Coughtrey & Pistrang, 2018  
- Verified Market Research, 2024  
- Grootendorst, 2022  
- Ma et al., 2025  


  # tambahin baris kosong biar ada perubahan
