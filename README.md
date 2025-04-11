# Dacon_HansolDeco_A3

## 📌 프로젝트 개요
건설안전지침 PDF 데이터를 기반으로, 전처리된 데이터를 FAISS VectorStore에 저장하고  
파인튜닝된 KoBART 모델과 함께 RAG(Retrieval-Augmented Generation)를 구성하여  
건설 현장의 질의에 대한 응답 문장을 생성하는 시스템입니다.

---

## 📁 폴더 및 파일 구조

### 0. 실행 방법
- `RAG.ipynb` 파일을 실행하여 전체 파이프라인을 수행할 수 있습니다.

### 1. `VectorStore/`
- FAISS를 이용해 구축된 벡터 DB
  - `Title_DB`: PDF 제목을 저장한 DB
  - `Content_DB`: PDF 본문 내용을 저장한 DB

### 2. `Model/`
- 파인튜닝된 모델이 저장된 폴더  
  ⚠️ GitHub 용량 제한으로 인해 일부 모델 파일은 제거되었습니다.  
  자세한 내용은 `Model/kobart7/MODEL_NOTICE.txt`를 참고해주세요.

### 3. `TestScore/`
- 검증 데이터(val)를 사용하여 파인튜닝된 모델의 성능을 평가한 `.csv` 파일이 포함되어 있습니다.

### 4. `Submission/`
- `sample_submission.csv`: 베이스라인 제출 형식
- `kobart7_submission.csv`: 파인튜닝 모델의 추론 결과 및 벡터 저장 파일

### 5. `RAG.ipynb`
- VectorStore에서 검색한 내용을 바탕으로 파인튜닝 모델을 이용해 결과 문장을 생성
- 주요 연관 파일:
  - `test_preprocessing.csv`: 전처리된 테스트 파일
  - `kobart7/`: 파인튜닝된 모델 경로
  - `Title_DB/`, `Content_DB_300_50/`: 각각 제목 및 본문 FAISS DB
  - `kobart7_submission.csv`: 생성된 응답 결과

### 6. `ModelFinetuning.ipynb`
- KoBART 기반 모델 파인튜닝 및 검증 데이터 평가 수행
- 주요 연관 파일:
  - `train_preprocessing.csv`, `test_preprocessing.csv`
  - `kobart7_eval.csv`: 검증 결과 파일

### 7. `PreprocessData.ipynb`
- 전처리 및 데이터 전수조사 수행 notebook
- 원본 데이터:
  - `train.csv`, `test.csv`

---

## ❗주의사항

- 실행 파일 중 `건설안전지침/` 폴더와 `DB/` 폴더는 GitHub의 업로드 용량 제한을 초과하여 `.gitignore`를 통해 커밋에서 제외되었습니다.
  - `건설안전지침/`: 총 104개의 건설안전지침 PDF 파일이 저장되어 있는 폴더입니다.
  - `DB/`: 전처리된 `train.csv` 및 `test.csv` 파일이 포함되어 있는 폴더입니다.

---

## ⚙️ 실행 환경 정보

### Python 패키지 버전

- `torch==2.6.0+cu124`
- `pandas==2.2.2`
- `tqdm==4.67.1`
- `transformers==4.50.0`
- `sentence_transformers==3.4.1`
- `langchain==0.3.21`
- `langchain_community==0.3.20`
- `langchain_huggingface==0.1.2`
- `numpy==2.0.2`
- `scikit-learn==1.6.1`
- `datasets==3.4.1`
- `koreanize-matplotlib==0.1.1`
- `seaborn==0.13.2`
- `matplotlib==3.10.0`

### 시스템 환경

- 운영체제: **Linux**
- Python 버전: **3.11.11**
- CPU: **Intel(R) Xeon(R) CPU @ 2.30GHz**
- GPU: **Tesla T4**
- 메모리: **13GB (13290460 kB)**

---

## 📩 참고사항

본 프로젝트의 파인튜닝된 모델 파일 및 일부 대용량 폴더는 GitHub의 업로드 용량 제한(100MB)을 초과하여  
레포지토리에서 제외되었습니다.  
제외된 모델 파일 관련 자세한 사항은 [`Model/kobart7/MODEL_NOTICE.txt`](Model/kobart7/MODEL_NOTICE.txt)를 참고해주세요.
