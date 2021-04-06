# NLP. Data preprocessing 
`Going Deeper에서 키워드 중심으로 뽑아서 관련한 추가 자료를 찾아 정리해나갈 예정입니다. 참고 교재를 아직 못 정했습니다.` 
    

## Lecture1. 텍스트 데이터 다루기 
* **전처리(Preprocessing): Natural language에서 Noise, Regex(정규표현식)**
* 표현(Representation): 희소 표현, 분산 표현
* Representation 관련 논문: [Subword-level Word Vector Representations for Korean](https://www.aclweb.org/anthology/P18-1226.pdf)
* 해당 논문 리뷰: https://brunch.co.kr/@learning/7
* 유사도 기법: 코사인 유사도  
* 맥락: 단어 표현에서 맥락 표현까지 
* 토큰화 기법: 공백(주로, 영어), 형태소(한국어), OOV
* Wordpiece Model(WPM): Byte Pair Encoding(BPE)에서 WPM
* BPE 관련 논문: [Neural Machine Translation of Rare Words with Subword Units](https://arxiv.org/pdf/1508.07909.pdf)
* WPM 관련 논문: [JAPANESE AND KOREAN VOICE SEARCH] (https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/37842.pdf)
* 임베딩 기법: Word2Vec, CBOW, Skip-gram, FastText, ELMo, BERT
  



## Wikidocs

* [딥러닝을 이용한 자연어 처리 입문](https://wikidocs.net/22660)
* 목차
	- **텍스트 전처리**
		- Tokenization 
		- Stemming and Normalization
		- Stemming and Lemmatization
		- Stopword
		- Regular Expression
		- Integer Encoding 
		- Padding 
		- One-hot encoding 
		- Splitting data 
		- Text preprocessing Tools for Korean text
    
### Tokenization 
#### Text data
1. Corpus: 정제되지 않은 말뭉치
2. Token: 최소 단위
	* 상황따라 최소 단위의 기준은 달라질 수 있다. e.g. 영어: 단어, 한국어: 형태소
	* 문장도 Token이 될 수 있다. 
3. Punctuation(구두점): . , ? ; !
4. Whitespace(띄어쓰기): 단어가 토큰일 때 데이터 전처리단에서 seperator/boundary(분리자/구분자)로 많이 사용
   
#### Tokenization is ... 
* Corpus to Token 
  
#### Tokenizer
* NLTK: for English e.g. Don't => 'Do', "n't"
* WordPunctTokenizer: for English e.g. Don't => 'Don', "'", 't'
* text_to_word_sequence in Tensorflow.keras.preprocessing e.g. Don't => Don't 

#### Standard Tokenizer
* TreebankWordTokenizer: Penn Treebank Tokenization
	- 규칙 1. hypen으로 구성된 단어는 하나로 유지한다.
	- 규칙 2. doesn't와 같이 아포스트로피로 '접어'가 함께하는 단어는 분리해준다.

#### Difficulty in Korean tokenization 
* 교착어이다. 어절이 독립적인 단어로 구성된 영어와 달리, 조사나 다른 무언가가 붙어있는 경우가 많다. 
* 띄어쓰기가 잘 키져지지 않는다. 띄어쓰기 없이도 문장 이해가 가능해서 띄어쓰기가 틀릴 때가 많다. 
* Part-of-speech tagging(품사태깅)의 어려움: 품사에 따라 단어 의미가 달라질 수 있다. e.g. 망치와 '못', '못'하다. 

#### Morpheme(형태소) Tokenizer in Korean 
* Okt
* Mecab: less time
* Komoran
* Hannanum
* Kkma