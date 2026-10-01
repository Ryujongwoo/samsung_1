77일차 수업 내용입니다.

# AI_LangGraph 가상환경 라이브러리 설치

AI_RAG 가상 환경에 설치한 라이브러리를 모두 설치하고 LangGraph에 관련된 라이브러리만 추가로 설치한다.

LangChain 0.3.x 시리즈와 가장 안정적으로 호환되는 버전은 langgraph>=0.2.0,<0.3.0 이다.  
langgraph-checkpoint 라이브러리는 상태(State)를 지속 유지하거나 복원해야 하는 경우 설치한다. 귀찮으니 다 설치하자.  

pip install "langgraph>=0.2.0,<0.3.0" "langgraph-checkpoint>=2.0.0" 
