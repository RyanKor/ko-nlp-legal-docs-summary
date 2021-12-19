# Legal document summary model natural language middle AI

![image](https://user-images.githubusercontent.com/40455392/144733715-60432bb5-bb45-4fd0-a580-edf06265fba1.png)

The task of extracting and summarizing the three sentences that best represent the original text of a Korean legal document

- Project Link : [Click (Described as Korean)](https://aihub.or.kr/problem_contest/nipa-learning-platform/5)

- Project Period : 10th December 2021 ~ 16th December 2021

## 1. Data Description
### Input & Output

- Input: Original text of legal documents divided by sentences (Example: [Sentence 1, Sentence 2, ..., Sentence K], K: Document length)
- Output : 3 sentence indexes to be included in the summary sentence
- Data organization
- Total about 14MB based on zip
- Train
- csv file containing 24,027 `legal document IDs ('id')`, `original text ('article_original')`, and `summary index ('extractive')`
- Test
- csv file containing 3,004 `legal document IDs ('id')` and `original text ('article_original')`



## 2. Expected WorkFlow

- Select Model Candidates (GPT-2 or beomi/KcELECTRA-base)
- EDA
- Training Model
- Predict & Evaluate Model

```
Working Directory

| - EDA.ipynb
| - ko_nlp_legal_docs_torch.ipynb
| - ko_nlp_legal_docs_train.ipynb
| - ko_nlp_legal_docs_gpt.ipynb
| - Readme.md
| - .gitignore
| - base_code
	| - [자연어]미들AI-법률문서요약 baseline (1).ipynb
| - data
	| - train.json
	| - test.json
	| - sample_submission.csv
	| - prediction.csv
```



- EDA.ipynb : This is Basic Exploratory Data Analysis Files of the dataset. Check word distribution per row & sentences, and the location of extractive label in the sentences.
- ko_nlp_legal_docs_torch.ipynb : base code with beomi/KcELECTRA-base
- ko_nlp_legal_docs_train.ipynb : my code trying to write TF with GPT-2 (It failed)
- ko_nlp_legal_docs_gpt.ipynb : base code with torch with GPT-2

- base_code : base line codes with blank (it uses the beomi/KcELECTRA-base model)

- data : contain train & test.json, sample_submission.csv files.



## 3. EDA

### 3-1) Analyze the number of sentences of the whole data.

- Basically, the sentence distribution consists of the graph below.
- Most of the sentences is less than 10, and the maximum length is 50.

![image](https://user-images.githubusercontent.com/40455392/146676666-176ec68e-072a-4a3f-bb82-cf39b00cc4d8.png)

## 3-2) The number of words.

- The word distribution consists of the histogram below.
- Most of the words is less than 200, and the maximum length is over 800.

![image](https://user-images.githubusercontent.com/40455392/146676810-561b9d98-d644-487b-9943-47505a21c9e3.png)



## 3-3) Distribution of Extractive label's location

- This graph is the core points of this projects.
- Most of labels are located in the beginning of the sentences, which means legal docs dataset contains their summary at the headline.
- This project is not "Abstractive Text Summarization" 

![image](https://user-images.githubusercontent.com/40455392/146676798-d57ac904-348b-4eef-852a-2b97d89f39b5.png)



## 3-4) Most Frequent Wrods in Extractive & Non-Extractive sentences

- This is not nessesary EDA, but I can gues which words frequently appear in extractive and not extractive summaries.

![image](https://user-images.githubusercontent.com/40455392/146677007-fad76878-b84a-4cdb-b473-6b2a1e49de61.png)



## 4. Project Logs

- First, I have participated in only classification projects before, this is completely different one to extract 3 core sentences to train the data.
- Second, There are not enough similar project reviews in google, most peopel tries to make 3 sentences with text rank algorithms (this is completely what I am not looking for)
- I can appoach this using GPT-2 or BERT (BERT is too heavy, so I changed to DistilBERT), but I have no idea how to mapping 3 extractive labelings with each sentences in the row.
- Baseline codes were written with pytorch, it makes more difficult to understand this project because I am not accustomed to that framework.



## 5. Reference

- [Zoom extractive summary post](https://blog.est.ai/2021/06/news-summary/)

- [Dacon Participation Post](https://tfrecord.tistory.com/16)

- [Korean Extractive Summary Bot with BERTSum](https://velog.io/@raqoon886/KorBertSum-SummaryBot)