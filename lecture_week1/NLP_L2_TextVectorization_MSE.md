# NLP. Text Vectorization
* 부교재: Wikidocs

## Lecture2. 텍스트 데이터 다루기 
* 단어 벡터화 	
  - Bag of Words
    - DTM(Document-Term Matrix)과 Cosine Similarity
  - TF-IDF(Term Frequency - Inverse Document Frequency)
  - LSA
  - LDA
    
* 텍스트 분포를 이용한 비지도 학습 토크나이저
  - 형태소 분석기와 단어 미등록 문제    
  - soynlp

## [Wikidocs](https://wikidocs.net/22660)
* Vector Similarity
  - Cosine Similarity
  - Others 
* Topic Modeling 
  - Latent Semantic Analysis(LSA, 잠재 의미 분석)
  - Latent Dirichlet Allocation(LDA, 잠재 디리클레 할당)
---
### Text Vectorization 
* 벡터화: 
* Vocaburaray(단어사전/집합): NLP에서 단어사전은 우리가 사전에 알고 있는 단어들의 집합을 의미합니다. BoW처럼 frequency로 정수인코딩해서 단어사전을 구성할 수도 있지만 두 개가 같은 개념은 아닙니다.

#### Bag of Words(BoW)
* 문장을 단어들의 문맥이나 순서는 무시하고 frequency(빈도수)를 기준으로 feature를 만드는 모델
  - 중복을 제거하지 않고 frequency를 센다. 
* 구현 관련 라이브러리: keras의 Tokenizer, scikit-learn의 CountVectorizer

#### DTM(Document-Term Matrix)
* 여러 문서의 BoW를 하나의 행렬로 구현한 것이다. 
* 일반적으로 문서를 행으로, 단어를 열로 가지는 행렬로 구성한다. 
* 문서를 열로, 단어를 행으로 한 경우는 TDM(Term-Document Matrix)이라고 부르기도 한다.  