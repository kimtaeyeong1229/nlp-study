# nlp-study

자연어처리(NLP)를 기초부터 차근차근 공부하며 정리하는 저장소입니다.
개념 정리, 실습 노트북, 실험 코드를 함께 쌓아갑니다.

## 학습 로드맵

| 단계 | 주제 | 핵심 키워드 |
|------|------|-------------|
| 1 | 텍스트 전처리 | 정규화, 토큰화, 불용어, 형태소 분석 (KoNLPy) |
| 2 | 단어 표현 | BoW, TF-IDF, N-gram |
| 3 | 워드 임베딩 | Word2Vec, GloVe, FastText |
| 4 | 시퀀스 모델 | RNN, LSTM, GRU, Seq2Seq |
| 5 | 어텐션과 트랜스포머 | Attention, Self-Attention, Transformer |
| 6 | 사전학습 모델 | BERT, GPT, 파인튜닝 |
| 7 | 응용 태스크 | 분류, 개체명 인식, 요약, 질의응답 |

## 디렉터리 구조

```
nlp-study/
├── notebooks/    # 실습 Jupyter 노트북
├── notes/        # 개념 정리 문서
├── src/          # 재사용 가능한 코드
└── data/         # 데이터셋 (git 추적 제외)
```

## 환경 설정

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## 진행 기록

학습하면서 정리한 내용은 `notes/`에, 직접 돌려본 코드는 `notebooks/`에 단계별로 추가합니다.
