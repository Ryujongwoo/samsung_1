71일차 수업 내용입니다.

# AI_RAG 라이브러리 설치

## Conda 기반 하드웨어/시스템 라이브러리 설치
LangChain을 제외한 데이터 처리, 벡터 DB, 모델 관련 기초 라이브러리를 Conda로 먼저 설치한다.

conda install -c conda-forge numpy=1.26.4 faiss-cpu python-dotenv openpyxl pypdf bs4 tiktoken transformers langdetect gradio

## Pip 기반 패키지 및 LangChain 생태계 일괄 설치
LangChain 핵심 패키지와 모든 LLM 제공자 패키지를 pip으로 한 번에 설치한다.

pip install "langchain>=0.3.0,<0.4.0" "langchain-core>=0.3.0,<0.4.0" "langchain-community>=0.3.0,<0.4.0" "langchain-text-splitters>=0.3.0,<0.4.0" "langchain-experimental>=0.3.0,<0.4.0" "langchain-openai" "langchain-anthropic" "langchain-chroma" "langchain-huggingface" "langchain-ollama" "langchain-google-genai" "langchain-groq" "pydantic>=2.7.0,<3.0.0" "anthropic>=0.30.0" google-genai groq krag kiwipiepy rank_bm25 jq


## 시작 환경 없음 메시지 창이 실행되면서 롤백되면 아래와 같이 처리한 후 설치한다.

<img src="./시작지점없음.png" />

관련 라이브러리 패키지 재설치  
문제가 발생하는 GDK 및 GLib 관련 패키지를 conda-forge 채널에서 최신 버전으로 재설치한다.

conda install -c conda-forge gdk-pixbuf glib gettext --force-reinstall

가상환경 내 전체 패키지 업데이트

conda update --all -c conda-forge
