# 주차별 의존성

각 주차 파일은 **이전 주차를 포함**하는 체인 구조입니다.

```
base.txt ← week01.txt ← week02.txt ← ... ← week12.txt
```

따라서 원하는 주차 파일 **하나만** 설치하면 그 주차까지 필요한 모든 패키지가 들어옵니다.
중간부터 합류하는 사람도 앞 주차를 순서대로 설치할 필요가 없습니다.

## 사용법

```bash
conda activate nlp-study

# 1주차만 필요한 경우
pip install -r requirements/week01.txt

# 5주차까지 한 번에
pip install -r requirements/week05.txt

# 전체 (= week12.txt)
pip install -r requirements.txt
```

## 주차별 추가 패키지

| 주차 | 주제 | 새로 추가되는 패키지 |
|------|------|----------------------|
| base | 공통 | numpy, pandas, matplotlib, jupyterlab, ipykernel, tqdm |
| 1 | 토큰화/서브워드 | tokenizers, transformers, sentencepiece, konlpy |
| 2 | 임베딩 + RNN·LSTM | **torch**, gensim, scikit-learn |
| 3 | SMT + BLEU | sacrebleu, nltk |
| 4 | Seq2Seq | datasets |
| 5 | Attention | — (직접 구현) |
| 6 | GNMT | — (논문 분석 중심) |
| 7 | Transformer 구조 | einops |
| 8 | Transformer 실습 | tensorboard |
| 9 | 사전학습 + MASS | accelerate, evaluate |
| 10 | BART | rouge-score |
| 11 | 다국어 + mBART | sacremoses |
| 12 | T5 / mT5 | — |

5·6·12주차는 새로 설치할 게 없습니다. 그래도 파일은 만들어 두었으니
`week05.txt`처럼 주차 번호만 바꿔 쓰면 항상 동작합니다.

## 별도 설치가 필요한 것

**Java (konlpy 실습용, 1주차 6.5)** — pip으로는 설치되지 않습니다.

konlpy는 내부적으로 Java 기반 형태소 분석기(Okt 등)를 호출합니다.

```bash
conda install -n nlp-study -c conda-forge openjdk -y
```

설치하면 `conda activate nlp-study` 시 `JAVA_HOME`이 자동으로 설정되므로
별도 환경변수 설정은 필요 없습니다. conda 환경 안에만 들어가므로 시스템 Java와 충돌하지 않습니다.

> JDK 25 + JPype 조합에서 `WARNING: A restricted method in java.lang.System has been called`
> 경고가 출력되지만 동작에는 문제가 없습니다.

**고전 SMT 툴킷 (3주차)**

Moses, GIZA++는 pip으로 설치되지 않고 직접 빌드해야 합니다.
3주차는 개념 이해가 목적이므로 설치하지 않아도 됩니다.

## 버전 고정에 대해

학습용 저장소라 버전을 고정하지 않았습니다.
발표 환경을 재현해야 한다면 그 시점에 `pip freeze > requirements/lock.txt`로
스냅샷을 남기는 것을 권합니다.
