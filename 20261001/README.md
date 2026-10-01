77일차 수업 내용입니다.

# AI_LangGraph 가상환경 라이브러리 설치

AI_RAG 가상 환경에 설치한 라이브러리를 모두 설치하고 LangGraph에 관련된 라이브러리만 추가로 설치한다.

LangChain 0.3.x 시리즈와 가장 안정적으로 호환되는 버전은 langgraph>=0.2.0,<0.3.0 이다.  
langgraph-checkpoint 라이브러리는 상태(State)를 지속 유지하거나 복원해야 하는 경우 설치한다. 귀찮으니 다 설치하자.  

pip install "langgraph>=0.2.0,<0.3.0" "langgraph-checkpoint>=2.0.0" 

# 라이브러리 설명

## AI & 데이터 처리

`numpy`: 고성능 수치 계산 및 다차원 배열(행렬) 처리를 위한 핵심 라이브러리  
`pandas`: 표 형태의 데이터(CSV, Excel 등)를 효율적으로 다루기 위한 데이터 분석/조작 라이브러리  
`pytorch`: 딥러닝 모델을 구축, 학습, 추론하기 위한 대표적인 오픈소스 프레임워크

## LLM / NLP(자연어 처리) & 임베딩

`transformers`: Hugging Face에서 제공하는 라이브러리로, BERT, GPT, LLaMA 등 최신 트랜스포머 기반 AI 모델을 손쉽게 로드하고 활용할 수 있다.  
`tiktoken`: OpenAI 모델(GPT-3.5, GPT-4 등)에서 텍스트를 토큰으로 분할(Tokenization)할 때 사용하는 토크나이저 라이브러리  
`faiss-cpu`: Meta(Facebook)에서 개발한 고성능 벡터 유사도 검색 라이브러리(CPU 전용)  
`langdetect`: 입력된 텍스트가 어떤 언어로 작성되었는지(한국어, 영어 등) 자동으로 감지하는 라이브러리

## 데이터 수집 & 파싱(문서/웹)

`pypdf`: PDF 파일에서 텍스트를 추출하거나 페이지를 분할/합치는 등 PDF 문서를 다루는 라이브러리  
`openpyxl`: Python으로 Excel 파일(.xlsx)을 읽고 쓰거나 수정할 수 있게 해주는 라이브러리  
`bs4(BeautifulSoup4)`: HTML/XML 문서 구조를 분석하고 웹 스크래핑을 통해 원하는 데이터를 추출할 때 사용한다.

## UI & 개발 편의 도구

`gradio`: 몇 줄의 Python 코드만으로 AI 모델이나 함수를 위한 인터랙티브 웹 UI 데모 페이지를 빠르게 만들어주는 프레임워크  
`ipywidgets`: Jupyter Notebook 환경에서 슬라이더, 버튼, 텍스트 상자 등 위젯을 추가해 동적인 인터페이스를 구성하게 해준다.  
`nbclassic`: Jupyter Notebook 6(구버전 classic)의 인터페이스를 최신 Jupyter 환경에서도 유지하여 사용할 수 있게 도와주는 패키지  
`tqdm`: Python 반복문(loop) 실행 시 진행 상태바(Progress Bar)를 시각적으로 보여주는 디버깅/진행 상황 파악용 라이브러리  
`python-dotenv`: 프로젝트 환경 변수(API 키, 데이터베이스 비번 등)를 .env 파일에 저장하고 안전하게 읽어오는 설정 관리 도구

## LangChain 프레임워크 코어(v0.3 기준 모듈화)

`langchain`: 프레임워크의 메인 패키지로, 에이전트 루프 및 전체 파이프라인 조립 인터페이스를 제공한다.  
`langchain-core`: 체인, 프롬프트, LLM, 출력 파서 등의 핵심 추상화 객체와 LCEL(LangChain Expression Language)의 기초를 제공하는 lightweight 핵심 패키지  
`langchain-community`: 서드파티 제3자 integration(다양한 데이터 로더, 툴, 벡터 DB 연동 모듈 등)을 모아둔 집합체  
`langchain-text-splitters`: 긴 문서나 텍스트를 LLM 및 벡터 DB 입력 크기에 맞게 효율적으로 분할(Chunking)하는 유틸리티 패키지  
`langchain-experimental`: 실험적인 기능, 고급 에이전트(e.g., Python REPL executor, SQL agent 등) 및 연구 단계의 코드를 모아놓은 패키지

## LLM 제공자 연동

`langchain-openai`: OpenAI 모델(GPT-4o, DALL-E, Text-Embedding 등)을 LangChain 규격으로 다루기 위한 공식 연동 패키지  
`langchain-anthropic`: Anthropic의 Claude 모델 시리즈를 연동하는 공식 패키지  
`langchain-google-genai`: Google Gemini 모델을 LangChain 환경에서 연동하기 위한 통합 패키지  
`langchain-groq`: Ultra-fast LPU 인퍼런스 엔진인 Groq 기반 모델들을 LangChain에서 연동하는 패키지  
`langchain-huggingface`: Hugging Face의 로컬/호스팅 오픈소스 LLM 및 임베딩 모델을 다루는 패키지  
`langchain-ollama`: 로컬 컴퓨터에서 Ollama로 실행 중인 오픈소스 모델(Llama 3, Qwen 등)을 연결하는 패키지  
`google-genai`: Google의 최신 공식 Gemini API 파이썬 SDK  
`groq`: Groq Cloud API를 직접 다루는 공식 파이썬 SDK  
`anthropic`: Claude API를 직접 호출하기 위한 공식 Anthropic 파이썬 SDK

## 워크플로우 & 고급 에이전트(LangGraph)

`langgraph`: 그래프 구조(Node, Edge) 기반으로 순환(Loop) 및 상태(State)가 존재하는 복잡한 LLM 워크플로우를 구현하는 프레임워크  
`langgraph-checkpoint`: LangGraph 실행 중 에이전트의 상태를 저장하고, 단계를 되돌리거나, 사람의 승인을 받는 인터랙션을 가능케하는 지속성 상태 저장소 라이브러리  

## RAG, 검색 및 임베딩(Retrieval & Search)

`langchain-chroma`: 오픈소스 대표 벡터 데이터베이스인 ChromaDB를 LangChain과 연결하는 공식 패키지  
`sentence-transformers`: 문장 및 단락 단위의 고성능 임베딩 벡터 생성 모델(Hugging Face 기반)을 로컬에서 실행하는 라이브러리  
`rank_bm2`5: 키워드 기반 전통적 검색 알고리즘인 BM25를 구현한 라이브러리로, 벡터 검색과 조합하여 하이브리드 검색을 구현할 때 필수적으로 사용된다.  
`krag`: Knowledge-graph/RAG 연관 특화 라이브러리

## 한국어 NLP & 데이터 가공(Parsing & Tokenization)

`kiwipiepy`: C++로 작성된 초고속 형태소 분석기 Kiwi의 파이썬 바인딩입니다. 한국어 텍스트 분할, 키워드 추출, 토큰화 처리에 주로 사용된다.  
`jq`: JSON 포맷 데이터를 고속으로 질의하고 조작/필터링하는 파이썬 패키지(C 파서 바인딩)  
`pydantic`: 데이터 검증 및 설정 관리를 위한 필수 라이브러리로, LLM 출력 결과의 구조화(Structured Output/JSON Parsing)를 강제할 때 핵심적인 역할을 담당한다.
