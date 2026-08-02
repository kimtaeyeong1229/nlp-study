# nlp-study

자연어처리(NLP)를 기초부터 차근차근 공부하며 정리하는 저장소입니다.
개념 정리, 실습 노트북, 실험 코드를 함께 쌓아갑니다.

## 학습 로드맵 — 기계번역(MT) 12주 커리큘럼

CV(CNN·ResNet) 배경은 있으나 NLP는 처음인 청중을 대상으로,
통계 기반 번역부터 사전학습 seq2seq 모델까지 12주에 걸쳐 다룹니다.

| 주차 | 주제 | 핵심 키워드 | 노트 | 실습 |
|------|------|-------------|------|------|
| 1 | NLP 입문 + 토큰화/서브워드 | 이산 심볼, 어휘, OOV, BPE | [📄](notes/01-nlp-intro-tokenization.md) | [📓](notebooks/01_tokenization.ipynb) |
| 2 | 단어 임베딩 + RNN·LSTM | Word2Vec, 시퀀스 모델링, gradient 소실 | |
| 3 | SMT & Phrase-based SMT + 평가 | 통계 기반 번역, 정렬, BLEU | |
| 4 | RNN Encoder–Decoder & Seq2Seq | 컨텍스트 벡터, teacher forcing | |
| 5 | Attention: Bahdanau & Luong | 정렬 학습, additive vs multiplicative | |
| 6 | GNMT | 실서비스 NMT, WordPiece, 딥 스택 | |
| 7 | Transformer (1) 구조 | Self-attention, multi-head, positional encoding | |
| 8 | Transformer (2) 구현·실습 | 마스킹, 학습 스케줄 | |
| 9 | 사전학습 패러다임 + MASS | BERT/GPT 개요, seq2seq 사전학습 | |
| 10 | BART | denoising autoencoder | |
| 11 | 다국어 NMT + mBART | massively multilingual, zero-shot | |
| 12 | T5 & mT5 + 전체 정리 | text-to-text 통합 관점 | |

## 디렉터리 구조

```
nlp-study/
├── notebooks/  # 주차별 실습 노트북
├── notes/      # 주차별 개념 정리 문서
└── data/       # 데이터셋 (git 추적 제외)
```

## 환경 설정

conda 환경 `nlp-study` (Python 3.11) 하나만 만들어 두고 씁니다.

```bash
conda create -n nlp-study python=3.11 -y
conda activate nlp-study
pip install jupyterlab ipykernel
python -m ipykernel install --user --name nlp-study --display-name "Python (nlp-study)"
```

**의존성 파일은 따로 두지 않습니다.** 각 노트북 첫 셀에 그 주차에 필요한 패키지 설치가 들어 있으니,
노트북을 열고 위에서부터 실행하면 됩니다.

pip으로 해결되지 않는 것만 아래에 적어 둡니다.

| 필요한 것 | 언제 | 설치 |
|-----------|------|------|
| JDK (konlpy용) | 1주차 실습 4 | `conda install -n nlp-study -c conda-forge openjdk -y` |

## 진행 기록

학습하면서 정리한 내용은 `notes/`에, 직접 돌려본 코드는 `notebooks/`에 단계별로 추가합니다.
