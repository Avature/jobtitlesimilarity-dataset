# Job Title Text Ranking Evaluation Dataset

This repository includes the English evaluation dataset used in the text ranking experiments reported in the paper *Learning
Job Titles Similarity from Noisy Skill Labels* by Rabih Zbib et al. [[1]](#citation). 

The task involves ranking a set of job titles, given another job title as query, such that the resulting ranking
reflects the semantic similarity of each job title to the query. To build the dataset, we started with 2,724 job titles
(short text phrases with the name of an occupation). After a minimal pre-processing, including clean-up and
lower-casing, we randomly divided the job titles into two groups: 105 job titles were used as queries, and the remaining
as corpus documents. Each query/document pair was labeled for binary relevance after adjudicating two independent
human annotations. (The inter-annotator agreement for this binary relevance labels was 86%.) 

The result is a dataset composed of the following files:

 - **corpus_documents.tsv**: includes the mapping between `corpus_document_id` to the text form of each job title in
                             the corpus.
 - **queries.tsv**: includes the mapping between `query_id` to the text form of each query job title.
 - **annotations.tsv**: includes the binary relevance annotations between. Only the relevant pairs are included, and the
                        file is formatted in the format required by `trec_eval` software library.


We also provide the translated datasets introduced in "Combined Unsupervised and Contrastive Learning for 
Multilingual Job Recommendations" by Deniz et al. [[2]](#citation). We replicate the English dataset for 
other languages by using Human Translation (HT) or Machine Translation (MT).

The datasets can be found under the [dataset/](./dataset) folder. Each dataset is under the folder with the ISO language 
code.


|           ISO code | Language   | Translation |
|-------------------:|:-----------|:-----------:|
|   [en](dataset/en) | English    |      -      |
|   [de](dataset/de) | German     |     HT      |
|   [es](dataset/es) | Spanish    |     MT      |
|   [fr](dataset/fr) | French     |     HT      |
|   [it](dataset/it) | Italian    |     MT      |
|   [ja](dataset/ja) | Japanese   |     HT      |
|   [ko](dataset/ko) | Korean     |     MT      |
|   [nl](dataset/nl) | Dutch      |     MT      |
|   [pl](dataset/pl) | Polish     |     MT      |
|   [pt](dataset/pt) | Portuguese |     MT      |
|   [zh](dataset/zh) | Chinese    |     HT      |


# Citation

[1] Rabih Zbib, Lucas Alvarez, Federico Retyk, Rus Poves, Juan Aizpuru, Hermenegildo Fabregat, Vaidotas Simkus,
Emilia Garcia Casademont: Learning Job Titles Similarity from Noisy Skill Labels. CoRR (2022)

[2] Daniel Deniz, Federico Retyk, Laura García-Sardiña, Hermenegildo Fabregat, Luis Gasco and Rabih Zbib:
Combined Unsupervised and Contrastive Learning for Multilingual Job Recommendation. HR@RecSys (2024)


```bibtext
@article{zbib2022Learning,
  author       = {Rabih Zbib and
                  Lucas Lacasa Alvarez and
                  Federico Retyk and
                  Rus Poves and
                  Juan Aizpuru and
                  Hermenegildo Fabregat and
                  Vaidotas Simkus and
                  Em{\'{\i}}lia Garcia Casademont},
  title        = {Learning Job Titles Similarity from Noisy Skill Labels},
  journal      = {CoRR},
  year         = {2022},
  url          = {https://doi.org/10.48550/arXiv.2207.00494},
  doi          = {10.48550/ARXIV.2207.00494},
}

@inproceedings{deniz2024Combined,
  author       = {Daniel Deniz and
                  Federico Retyk and
                  Laura García-Sardiña and
                  Hermenegildo Fabregat and
                  Luis Gasco and
                  Rabih Zbib},
  title        = {Combined Unsupervised and Contrastive Learning for Multilingual Job Recommendations},
  booktitle    = {Proceedings of the 4rd Workshop on Recommender Systems for Human Resources
                  (RecSys in {HR} 2024), in conjunction with the 18th {ACM} Conference on
                  Recommender Systems},
  year         = {2024},
}
```