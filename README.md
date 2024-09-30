# Job Title Text Ranking Evaluation Dataset

This repository provides **job title similarity** datasets in **11** different languages, including the English evaluation 
dataset used in the text ranking experiments reported in the paper _"Learning Job Titles Similarity from Noisy Skill
Labels"_ by Rabih Zbib et al. [[1]](#citation), as well as the translated datasets for the other languages introduced in
_"Combined Unsupervised and Contrastive Learning for Multilingual Job Recommendations"_ by Deniz et al. [[2]](#citation)

### Task Overview
The task involves ranking a set of job titles, given another job title as query, such that the resulting ranking
reflects the semantic similarity of each job title to the query. This requires identifying the most relevant job titles 
based on their semantic similarity to a given query.

### English Dataset Creation
The English dataset was built by starting with 2,724 job titles (short text phrases with the name of an occupation). 
Next, a minimal pre-processing step with light clean up was applied. The job titles were randomly divided into two groups: 
* 105 job titles were used as queries.
* The remaining job titles were used as corpus documents.

Each query/document pair was labeled for binary relevance after adjudicating two independent
human annotations. (The inter-annotator agreement for this binary relevance labels was 86%.) 

The result is a dataset composed of the following files:

 - **corpus_documents.tsv**: includes the mapping between `corpus_document_id` to the text form of each job title in
                             the corpus.
 - **queries.tsv**: includes the mapping between `query_id` to the text form of each query job title.
 - **annotations.tsv**: includes the binary relevance annotations between. Only the relevant pairs are included, and the
                        file is formatted in the format required by `trec_eval` software library.

### Translated Datasets
We also provide the translated datasets in 10 more additional languages. We replicate the English dataset for the 
other languages by using Human Translation (HT) or Machine Translation (MT).

The datasets can be found under the [dataset/](./dataset) folder. Each dataset is under the folder with their ISO 639-1 
two-character code.


|  ISO 6939-1 code | Language   | Translation |
|-----------------:|:-----------|:-----------:|
| [en](dataset/en) | English    |      -      |
| [de](dataset/de) | German     |     HT      |
| [es](dataset/es) | Spanish    |     MT      |
| [fr](dataset/fr) | French     |     HT      |
| [it](dataset/it) | Italian    |     MT      |
| [ja](dataset/ja) | Japanese   |     HT      |
| [ko](dataset/ko) | Korean     |     MT      |
| [nl](dataset/nl) | Dutch      |     MT      |
| [pl](dataset/pl) | Polish     |     MT      |
| [pt](dataset/pt) | Portuguese |     MT      |
| [zh](dataset/zh) | Chinese    |     HT      |


# Citation

[1] Rabih Zbib, Lucas Alvarez, Federico Retyk, Rus Poves, Juan Aizpuru, Hermenegildo Fabregat, Vaidotas Simkus, 
Emilia Garcia Casademont: Learning Job Titles Similarity from Noisy Skill Labels. FEAST, ECML-PKDD 2022 Workshop (2021)


[2] Daniel Deniz, Federico Retyk, Laura García-Sardiña, Hermenegildo Fabregat, Luis Gasco and Rabih Zbib:
Combined Unsupervised and Contrastive Learning for Multilingual Job Recommendation. HR@RecSys (2024)


```bibtext
@article{zbib2022Learning,
      title={{Learning Job Titles Similarity from Noisy Skill Labels}}, 
      author={Rabih Zbib and 
              Lucas Alvarez Lacasa and 
              Federico Retyk and 
              Rus Poves and 
              Juan Aizpuru and 
              Hermenegildo Fabregat and
              Vaidotas Šimkus and 
              Emilia García-Casademont},
      journal    = {{FEAST, ECML-PKDD 2022 Workshop}},
      year         = {{2022}},
      url = "https://feast-ecmlpkdd.github.io/archive/2022/papers/FEAST2022_paper_4972.pdf"
}


@inproceedings{deniz2024Combined,
  title        = {Combined Unsupervised and Contrastive Learning for Multilingual Job Recommendations},
  author       = {Daniel Deniz and
                  Federico Retyk and
                  Laura García-Sardiña and
                  Hermenegildo Fabregat and
                  Luis Gasco and
                  Rabih Zbib},
  booktitle    = {Proceedings of the 4th Workshop on Recommender Systems for Human Resources
                  (RecSys in {HR} 2024), in conjunction with the 18th {ACM} Conference on
                  Recommender Systems},
  year         = {2024},
}
```