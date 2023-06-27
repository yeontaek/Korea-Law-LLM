

## Update Logs
- 🤗Polyglot-ko 12.8B 기반 Law-Polyglot-12.8B QLoRa 4bit 모델 공개 예정
- 🤗Polyglot-ko 12.8B 기반 Law-Polyglot-12.8B LoRa 8bit 모델 공개 예정

---
<br>

# Korea Law Large Language Model

- 한국어 법률 데이터 기반으로 개발한 한국어 Large Language Model (LLM) 입니다.

## Polyglot-ko 12.8B

해당 모델의 모든 실험 Backbone Model은 [Polyglot-ko-12.8B](https://huggingface.co/EleutherAI/polyglot-ko-12.8b) 사용하여 진행하였습니다.

1. Polyglot-ko 12.8B LoRa 8bit -> 🤗 [Law-Polyglot-12.8B LoRa 8bit]()
    - 데이터셋 v1:
2. Polyglot-ko 12.8B QLoRa 4bit -> 🤗 [Law-Polyglot-12.8B QLoRa 4bit]()
    - 데이터셋 v1:


## 모델 실행 결과 예시

```
### 질문: 범죄를 저지르고 얻은 수입은 체포되면 어떻게 되는건가요?

### 답변: 미국을 비롯한 세계 각국에서는 유죄판결을 받은 범죄자의 범죄수익을 추적해 몰수하는 절차가 있다. 
우리나라에는 '범죄수익은닉의 규제 및 처벌 등에 관한 법률'(이하범죄수익은닉법)이 있으며, 몰수대상 재산에는 예금·부동산 등 재산 뿐 아니라 범죄수익도 포함되어 있다. 
또한 몰수 외에도 추징금, 과료(科料) 등 의 대체 집행방법이 있다. 범죄수익은닉법은 미국의 대표적인 '벌크캐시법(현금추방법)'을 수용한 것으로, 우리나라에도 미국과 유사한 내용의 범죄수익몰수법이 적용되고 있다.

```

## SFT(supervised-fine-tuning)

### 학습 데이터 구성

- 모든 SFT 학습 데이터 구성 방법은 [stanford alpaca](https://github.com/tatsu-lab/stanford_alpaca)과 동일하게 사용하였습니다.
- Stanford Alpaca의 학습 데이터 중 40%는 input 값을 입력하여 학습을 진행
  > input: str, optional context or input for the task. For example, when the instruction is "Summarize the following article", the input is the article. Around 40% of the examples have an input.
-

```
### Instruction:
{instruction}

### Input:
{input}

### Response:
```

```
### Instruction:
{instruction}

### Response:
```

### 학습 
- 모든 모델 학습은 A100 80GB 4대로 학습을 진행
- 

## RRHF(Rank Response from Human Feedback)

## Reference