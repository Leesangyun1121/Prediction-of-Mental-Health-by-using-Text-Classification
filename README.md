# Comparative Evaluation of Word Representation and Text Classification Algorithms for Predicting Mental Illness from Social Media

# 연구 개요
- 정신 질환을 예측하는 방법에는 여러가지 접근 방식이 있지만 그 중에서 텍스트 분류를 활용하여 예측  
- 세계적인 SNS Reddit 내 정신질환 서브레딧(r/ADHD, r/Anxiety, r/Bipolar, r/Depression, r/Schizophrenia)과 비정신질환 서브레딧(대조군 - r/fitness, r/jokes, r/meditation, r/parenting, r/relationship, r/teaching) 포스트를 사용  
- 3가지 임베딩 방식(Randomly initialized, Word2Vec, Fasttext)과 4가지 텍스트 분류 알고리즘(Ensemble, Bi-LSTM, Bi-LSTM with Attention, Self Attention)을 각각 조합하여 여러개의 모델을 제작한 후 성능 평가를 통해 가장 좋은 모델을 도출한 후 Test Text가 6개의 정신질환 관련 label에 속할 확률을 barchart로 시각화   


### 데이터셋 

**1) Original Data**
```
1) adhd_origin.csv: subreddit이 adhd인 데이터   
2) anxiety_origin.csv: subreddit이 anxiety인 데이터     
3) bipolar_origin.csv: subreddit이 bipolar인 데이터   
4) depression_origin.csv: subreddit이 depression인 데이터
5) schizo_origin.csv: subreddit이 schizophrenia인 데이터
6) non-health.csv: subreddit이 subreddit이 fitness, jokes, meditation, parenting, relationship, teaching인 대조군(정상군) 데이터
```
**2) 데이터 샘플**
| 	 |subreedit	|author	|title	|text_content	|date	|content|
|----|------|---------|---------------|---------|-----------|----------|   

**3) 데이터 사이즈**
| 	 |ADHD	|Anxiety	|Bipolar	|Depression	|Depression	|non-health    |
|----|------|---------|---------------|---------|-----------|--------------|
|Before Preprocessing|256065|298852   |162986	|720434	|60009	|425346	|  


### 데이터 전처리

**1) 데이터 전처리 항목**
```
1) Null 값 제거
2) 각 서브레딧 당 게시글이 10개 이상 작성한 사용자의 post 중 하나를 랜덤 추출
3) title과 text_content를 합친 'content' 행 만들기
4) ?/!/'를 제외한 특수문자 제거
5) Stopword 제거
6) 단어 단위로 토큰화
```
**3) 전처리된 데이터**
```
데이터 전처리 항목 1~5를 적용한 후 정리한 데이터

1) adhd_c.csv 
2) anxiety_c.csv   
3) bipolar_c.csv 
4) depression_c.csv
5) schizo_c.csv
6) nonM_c.csv
```


**4) 전처리된 데이터 사이즈**
| 	 |ADHD	|Anxiety	|Bipolar	|Depression	|Schizophrenia	|nonM    |
|----|------|---------|---------------|---------|-----------|--------------|
|After Preprocessing|94324|138824|37192|359368|13155|247569|

**5) 데이터 다운로드**
https://drive.google.com/drive/folders/11oM2Vn8DeJmzBThRklIVnLbXt8z3uljX?usp=sharing


