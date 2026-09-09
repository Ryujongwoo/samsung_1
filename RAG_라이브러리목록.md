# 01_LangChain의_주요_RAG_컴포넌트.ipynb  
 
import warnings # 경고 메시지 무시  
warnings.filterwarnings('ignore')  
import os # 운영체제  
from tqdm import tqdm # 진행 상태바  

from dotenv import load_dotenv # .env 파일의 환경변수 읽기  
from glob import glob # 패턴과 일치하는 파일 찾기  
load_dotenv()  
from langchain_community.document_loaders import TextLoader # 텍스트 문서 읽기  
from langchain_text_splitters import CharacterTextSplitter # 특정 구분자를 경계로 문서 나누기  
from langchain_openai import OpenAIEmbeddings # 임베딩 모델  
from langchain_chroma import Chroma # 크로마 벡터 저장소  

from langchain_openai import ChatOpenAI # LLM 모델  
from langchain_core.prompts import ChatPromptTemplate # 프롬프트 템플릿  

from langchain_classic.chains.combine_documents import create_stuff_documents_chain # 검색된 문서를 컨텍스트로 결합하고 체인 만들기  
from langchain_classic.chains import create_retrieval_chain # 검색된 문서를 바탕으로 RAG 만들기  
from langchain_core.documents import Document # 랭체인 표준 데이터 도큐먼트  

import gradio as gr # 챗봇 인터페이스  
***
<br>

# 02_LangChain의_LCEL_사용하기.ipynb

import time # sleep() 메소드 사용하기  
from operator import itemgetter # 딕셔너리에서 특정 key값 가져오기  
from pprint import pprint # 보기 좋게 출력  

from langchain_core.output_parsers import StrOutputParser # 응답 결과를 문자열만 얻어오기  
from langchain_core.output_parsers import JsonOutputParser # 응답 결과를 JSON 형태로 얻어오기  
from langchain_core.output_parsers import PydanticOutputParser # 응답 결과를 클래스 형태로 얻어오기  
from pydantic import BaseModel, Field, validator # 파이썬의 Pydantic 사용하기  
from langchain_core.runnables import RunnableParallel # 입력받은 데이터를 새 딕셔너리로 만들기  
from langchain_core.runnables import RunnablePassthrough # 데이터를 변형없이 그대로 사용하기  
from langchain_core.runnables import RunnableLambda # 사용자 정의 함수 실행 결과를 딕셔너리로 만들기  
***
<br>

# 03_데이터처리_및_임베딩기법.ipynb

import numpy as np # 넘파이

from langchain_community.document_loaders import PyPDFLoader # PDF 파일 읽기
from langchain_community.document_loaders import WebBaseLoader # 웹 문서 읽기
from langchain_community.document_loaders import JSONLoader # JSON, JSONL 파일 읽기
from langchain_community.document_loaders import CSVLoader # CSV 파일 읽기

from langchain_text_splitters import RecursiveCharacterTextSplitter # 재귀적으로 청크 분할
import tiktoken # OpenAI의 토큰화
from transformers import AutoTokenizer # 허깅 페이스 모델의 토크나이저 자동 불러오기
from langchain_experimental.text_splitter import SemanticChunker # 맥락 기반 분할
from langchain_community.utils.math import cosine_similarity # 코사인 유사도

from langchain_huggingface.embeddings import HuggingFaceEmbeddings # 허깅 페이스 임베딩 모델
from langchain_ollama import OllamaEmbeddings # 올라마 임베딩 모델
from langdetect import detect # 언어 판별
from langchain_core.messages import HumanMessage, AIMessage # 사용자 메시지, AI 메시지 객체








