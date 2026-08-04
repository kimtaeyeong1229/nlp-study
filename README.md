# nlp-study

자연어처리(NLP)를 공부하며 정리하는 저장소입니다. 개념 정리 글과 실습 노트북을 함께 쌓아갑니다.

## 1주차 — 텍스트 입력 파이프라인

`"Hello World!"`라는 문자열이 GPT-2에 들어가 임베딩 벡터가 되기까지의 네 단계를 다룹니다.

1. 토큰화(Tokenization)
2. 번호 매기기(Encoding)
3. 특수 토큰과 패딩(Special Tokens & Padding)
4. 임베딩 룩업(Embedding Lookup)

- 글 — [notes/01-input-pipeline.md](notes/01-input-pipeline.md)
- 실습 — [notebooks/01_input_pipeline.ipynb](notebooks/01_input_pipeline.ipynb)

## 디렉터리 구조

```
nlp-study/
├── notebooks/  # 실습 노트북
└── notes/      # 개념 정리 문서
```

## 환경 설정

conda 환경 `nlp-study` (Python 3.11) 하나만 만들어 두고 씁니다.

```bash
conda create -n nlp-study python=3.11 -y
conda activate nlp-study
pip install jupyterlab ipykernel
python -m ipykernel install --user --name nlp-study --display-name "Python (nlp-study)"
```

**의존성 파일은 따로 두지 않습니다.** 각 노트북 첫 셀에 필요한 패키지 설치가 들어 있으니, 노트북을 열고 위에서부터 실행하면 됩니다.

노트북은 토크나이저와 설정값만 내려받고 모델 가중치는 쓰지 않으므로 **GPU 없이 돌아갑니다.**
