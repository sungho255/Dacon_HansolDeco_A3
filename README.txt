# README
1. 프로젝트 설치 및 사용 방법
0) 실행 방법 : RAG.ipynb 실행
1) 건설안전지침 폴더 : 104개의 건설안전지침 PDF가 들어 있는 폴더
2) DB : 전처리한 train.csv와 test.csv가 들어 있는 폴더
3) VectorStore : FAISS를 사용하여 PDF의 제목을 저장한 Title_DB와 PDF내용을 저장한 Content_DB가 들어 있는 폴더
4) Model : 파인튜닝한 모델들이 들어 있는 폴더
5) TestScore : 파인튜닝한 모델을 val 데이터를 사용하여 평가한 csv 파일이 들어 있는 폴더
6) Submission : 기본 submisson csv(sample_submission.csv) 과 최종 제출 형태에 맞춰 파인튜닝 된 모델이 추론한 문장과 
		    Vector를 저장한 csv 파일이 들어 있는 폴더

7) RAG.ipynb : VectorDB로 부터 가져온 내용과 파인튜닝한 모델을 통해 추론하여 submission 결과 산출 +) VectorDB 저장
    7-1) test_preprocessing.csv: 전처리한 test.csv 파일
    7-2) kobart7: 파인튜닝한 모델명
    7-3) Title_DB: PDF 제목을 저장한 FAISS DB
    7-4) Content_DB_300_50: 300의 청크 Size와 50의 Overlap하여 PDF 내용을 저장한 FAISS DB 
    7-5) kobart7_submission.csv: 실행 시 추론한 vector 결과물
8) ModelFinetuning.ipynb: 전처리한 train 데이터를 사용한 kobart 모델 파인튜닝과 val 데이터를 사용하여 테스트 결과 산출
    8-1) train_preprocessing.csv: 전처리한 train.csv 파일
    8-2) test_preprocessing.csv: 전처리한 test.csv 파일
    8-3) kobart7: 파인튜닝한 모델명
    8-4) kobart7_eval.csv: val 데이터를 사용하여 테스트 결과물
9) PreprocessData.ipynb: 전처리를 위한 train 데이터 전수조사 결과
    9-1) train.csv: 전처리 전 train.csv 파일
    9-2) test.csv: 전처리 전 test.csv 파일

2. 환경 정보
torch==2.6.0+cu124
pandas==2.2.2
tqdm==4.67.1
transformers==4.50.0
sentence_transformers==3.4.1
langchain==0.3.21
langchain_community==0.3.20
langchain_huggingface==0.1.2
numpy==2.0.2
scikit-learn==1.6.1
datasets==3.4.1
koreanize-matplotlib==0.1.1
seaborn==0.13.2
matplotlib==3.10.0

3. 운영체제 
운영 체제 (OS) : Linux
Python 버전 : 3.11.11
CPU 아키텍처 : Intel(R) Xeon(R) CPU @ 2.30GHz
GPU :  Persistence-M(Tesla T4)
Memory : 13290460 kB
