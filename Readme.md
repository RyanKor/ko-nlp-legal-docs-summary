# Legal document summary model natural language middle AI

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

