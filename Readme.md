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

- Select Model Candidates (GPT-3 or Ko-GPT by Kakao Brain)
- EDA
- PreProcessing Text
- Training Model
- Predict & Evaluate Model

```
Working Directory

| - EDA.ipynb
| - ko_nlp_legal_docs_torch.ipynb
| - ko_nlp_legal_docs_train.ipynb
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

