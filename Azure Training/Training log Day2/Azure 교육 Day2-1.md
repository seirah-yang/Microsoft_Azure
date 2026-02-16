# Azure 교육 Day2-1

구조 전체트리: TDH Workspace
├─ Microsoft Foundry
├─ 에이전트
├─ Open AI
├─ 클로스 오퍼스 4-1
├─ Kimi K-2.5
└─ Deepseekv3.2

<aside>

### 1. AI의 개념

🔹 [Microsoft Certified: Azure AI 기본사항](https://learn.microsoft.com/ko-kr/credentials/certifications/azure-ai-fundamentals/?practice-assessment-type=certification) 

: AI 솔루션을 만들기 위한 Microsoft Azure의 소프트웨어 및 서비스 개발과 관련된 기본 AI 개념을 보여 줍니다.

**[필요한 개념]**

🔹 기본 클라우드 개념

🔹 클라이언트 서버 애플리케이션

**[시험실습]**

🔹 지식평가 및 실습 평가 수행 

🔹 데모 경험: 시험 중에 사용할 동일한 사용자 인터페이스로 다양한 문제 유형과 상호 작용 할 수 있다. → 샌드박스 

**[평가 영역]**

🔹 **인공 지능 워크로드 및 고려 사항** 설명

🔹 Azure에서 **기계 학습의 기본 원칙** 설명

🔹 Azure에서 **Computer Vision 워크로드의 기능** 설명

🔹 Azure에서 **NLP(자연어 처리) 워크로드의 기능** 설명

🔹 Azure에서 **생성 AI 워크로드의 기능** 설명

</aside>

<aside>

### 1. AI의 개념 소개

# [**Azure의 AI 소개**](https://learn.microsoft.com/ko-kr/training/courses/ai-900t00)

과정 AI-900T00-A: Azure의 AI 소개
본 과정에서는 인공 지능(AI)과 관련된 기본 개념과 AI 솔루션을 만드는 데 활용할 수 있는 Microsoft Azure의 서비스를 소개합니다. 본 과정은 전문 데이터 과학자나 소프트웨어 개발자가 되려는 학생들을 위한 것이 아니라 일반적인 AI 워크로드에 대한 인식과 이를 지원할 Azure 서비스를 식별할 수 있는 능력을 키우기 위한 것입니다. 이 과정은 강사 진행 교육과 Microsoft Learn 플랫폼([https://azure.com/learn](https://azure.com/learn))의 온라인 자료를 결합한 혼합 학습 환경으로 고안되었습니다. 본 과정의 실습 연습은 Learn 모듈을 기반으로 하며, 학습 내용을 참고 자료로 사용하여 수업에서 배운 내용을 보강하고 주제를 보다 심층적으로 탐구할 것을 권장합니다.

---

### **1) 목적: AI란 무엇인가요 ?**

**1️⃣ 인간의 능력을 모방하는 소프트웨어**

- 결과 예측 및 기록 데이터를 기반으로 패턴 인식
- 비정상적인 사건 인식, 의사결정 및 적절한 조치 수행
- 시각적 입력 해석
- 언어 이해 및 대화 참여
- 정보를 얻기 위해 원본에서 정보 추출

**2️⃣ AI의 분류** 

생성형 AI/에이전트 및 자동화/자연어/컴퓨터 피전/정보추출

머신러닝 >딥러닝  

|  | 내용 |
| --- | --- |
| **공정성** |  |
| **신뢰성과 안전성**  |  |
| **개인정보 및 보안** |  |
| **포용성**  |  |
|  |  |

### **2)** (AI-900) Microsoft Foundry 시작

1️⃣ **Azure AI 파운드리 → `Microsoft Foundry`(생성형 AI를 받을 수 있는 마지막 방법이다)**

가장 기본적인 **LLM 검색 프로세스**

<aside>

파운드리모델(GPT, Lama, … LLM) / Azure Open AI : 

  +

Azure 파운드리 에이전트 (에이전트 및 자동화)

  +

언어 / 번역기 / Speech 

  +

Vision(Comfuter Detection, OCR, 손글씨 인식 등)/ Face API

  +

Document Intelligence / Contents understanding /검색 

</aside>

</aside>

<aside>

### 2. Machine Learning의 개념 소개

---

**목적: Machine Learning의 개념에 대해서 알아봅시다.** 

### 1) [Machine learning vs Deep learning](https://learn.microsoft.com/en-us/azure/machine-learning/concept-deep-learning-vs-machine-learning?view=azureml-api-2)

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image.png)

Machine에게 수학(Data)를 가지고 교육을 시킨다 **→ Model** 

Algorigdm : 수학으로 교육을 시키는데 그때 주입하는 공식이 알고리즘 
  → 어떤 상황에서 어떤 알고리즘이 필요한지만 알면 된다. 

|  | Machine learning | Deep learning |
| --- | --- | --- |
| Number of data points | Can use small amounts of data to make predictions. | Needs to use large amounts of training data to make predictions. |
| Hardware dependencies | Can work on low-end machines. It doesn't need a large amount of computational power. | Depends on high-end machines. It inherently does a large number of matrix multiplication operations. A GPU can efficiently optimize these operations. |
| Featurization process | Requires features to be accurately identified and created by users. | Learns high-level features from data and creates new features by itself. |
| Learning approach | Divides the learning process into smaller steps. It then combines the results from each step into one output. | Moves through the learning process by resolving the problem on an end-to-end basis. |
| Training time | Takes comparatively little time to train, ranging from a few seconds to a few hours. | Usually takes a long time to train because a deep learning algorithm involves many layers. |
| Output | The output is usually a numerical value, like a score or a classification. | The output can have multiple formats, like a text, a score, or a sound. |

<aside>

### cf.  Geoffrey Everest Hinton

 ****[노벨 물리학상](https://www.google.com/search?sca_esv=c7a34cb64741ffad&sxsrf=ANbL-n5G3ElBZupwTIoSv5Zezgz3ylxaXg:1770858824983&q=%EB%85%B8%EB%B2%A8+%EB%AC%BC%EB%A6%AC%ED%95%99%EC%83%81&si=AL3DRZHmwLjWhgnaPB3UTu10R6S5qNLXiQiKMeezfKyB1FMsRmCmN6agrOb0DsURzlYWty_NxwoJqTcnTVdrOxp0Rh_r9QJiqJt8hbnBhk2Sc3-EAJF5EwdNQ5fD5x7ksHm6UiBfYS2y64vP6J2uaFOKtxy7DCdatJmx3xy2oZ_ADGPCLeE_Oj1QTToXmd7ZJU72_du1LKULFD6JYojtmNbwzimy8b_OxuhVbbGrfbNNYWljj_i4XoTDxWmsYVcOpeHvKxpdFRyZwZJV3j2TrF8QxhtiK243CA%3D%3D&sa=X&ved=2ahUKEwi5o9eZ49KSAxUoZ_UHHRJ5BlYQmxN6BAgbEAI), [튜링상](https://www.google.com/search?sca_esv=c7a34cb64741ffad&sxsrf=ANbL-n5G3ElBZupwTIoSv5Zezgz3ylxaXg:1770858824983&q=%ED%8A%9C%EB%A7%81%EC%83%81&si=AL3DRZHmwLjWhgnaPB3UTu10R6S5qNLXiQiKMeezfKyB1FMsRu2wCuMFHXj-L9P_q_uA85NXqN846b4fdGVrTZK2lUYPP9bEG1iYTZpEevErQYoK7EPTfnmN_T90ag70xfUFC6tIKPDtwPuSH4tOB61lTdKVq_d_9pVudv1ZQGigCXG0rERfY9bx_XA-GYp-ohizOrWs6-ftRB2cs1qcMb30b_WasFy2RD9WG3GJEPVd9aZbtO-e50nqSb8WUiiXPPlfgqKxGBzZ&sa=X&ved=2ahUKEwi5o9eZ49KSAxUoZ_UHHRJ5BlYQmxN6BAgbEAM) 

[Neural Network Architectures for Artificial Intelligence](https://www.google.com/search?sca_esv=c7a34cb64741ffad&sxsrf=ANbL-n5G3ElBZupwTIoSv5Zezgz3ylxaXg:1770858824983&q=%EC%A0%9C%ED%94%84%EB%A6%AC+%ED%9E%8C%ED%84%B4+neural+network+architectures+for+artificial+intelligence&si=AL3DRZHnaVpOpV17tK9mg6av50PE-kRfFRFUaAr9T0Uxmp5elSnK9q72cITRBZJgWgdUVM52UFtfWxYGHlEPtaXnb_rOBMS5fOh4eYIg7lcQAx0QD0vD24DzD5q-gjyNzaoTRXPnOXefgOwggetWk_DRH3kC5y7DwvPf2zoYpiqa_2XI9YVt0ndytUwDwz10SQfa1aHqleJmT6hugGuoLeOMobbtVYA5i18L9Yv6br3nhs8GY6wq00lTS17275z3ukrb76m8n2lJ8FUw3tJwPH-wtYEdH_ssIAA7M_6qKb5n9e2GFcmInA8%3D&sa=X&ved=2ahUKEwi5o9eZ49KSAxUoZ_UHHRJ5BlYQmxN6BAgdEAI)

***인공지능(AI) 분야를 개척한 영국 출신의 컴퓨터과학자***이자 인지과학자, 인지심리학자. 캐나다에 위치한 토론토 대학교에서 컴퓨터 과학 교수로 재직중이며 구글 브레인석학 연구원도 겸임했었으나 2023년 인공지능의 위험성에 대해 경고하며 퇴사.

</aside>

### 2) Azure에서 Machine Learning 시작

$f(x) = \hat y$

- labeling (예측하려는 항목)
    - x = year
    - y= salary

결론 : x 값을 넣으면 나오는 y값이 무엇인지를 예측하는 것 

```markdown
###  **maching learning** 
       
          **supervised**                            ** un-supervised** 
 regression       classification                   clustering 
               binary       multi class   

### 강화학습 
수천번 넘어지다가 한번 잘 딛고 일어나면 그때부터 강화학습 일어나면 폭풍성장
```

</aside>

---

<aside>

## 3. 머신러닝 - 회귀, 분류, 머신러닝, 딥러닝

[**Azure Algorithm Cheat Sheet**](https://learn.microsoft.com/en-us/azure/machine-learning/algorithm-cheat-sheet?view=azureml-api-1) 

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%201.png)

```markdown
### what do you want to do? 
→ 값을 예측하고 싶다  → Regression 
→ 
→ 
```

---

### Model Algorithm 및 평가 메트릭

재발 : MAE /MSE/ RMSE/ $R^2$

분류: 정확도/ 재현율/ 정밀도/ F1 Score 

클러스터링 

딥러닝은 각각의 노드에 가중치를 설정하는 단계 = 학습 

---

### 3-2. Azure Machine Learning

기계 학습을 위한 클라우드 기반 플랫폼 

studio

**자동화된 Machine learning 이란?** 

기계학습 훈련 작업을 실행하는 데 도움이 되는 단계별 마법사 

회귀, 시계열 예측, 분류, 컴퓨터 비전, 자연어 처리 작업을 비롯한 많은 기계 학습 작업을 지원

데이터에 연결하고, 학습 작업 및 대상 메트릭을 정의하고, 최상의 결과 모델을 배포 

</aside>

Azure에서 리소스 그룹 만들기 

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%202.png)

---

```markdown
### /subscriptions/14734032-3a81-427c-b9a7-6a15145822d4/resourceGroups/labuser9-rg
{
    "id": "/subscriptions/14734032-3a81-427c-b9a7-6a15145822d4/resourceGroups/labuser9-rg",
    "name": "labuser9-rg",
    "type": "Microsoft.Resources/resourceGroups",
    "location": "polandcentral",
    "tags": {},
    "properties": {
        "provisioningState": "Succeeded"
    }
}
```

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%203.png)

---

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%204.png)

---

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%205.png)

---

**Leanch Studio Clinck → Machinlearning Operation (MLOps가 기본적으로 되게 되어 있음)**

- 컴퓨팅 : 컴퓨팅 인스턴스 새로 만들기

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%206.png)

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%207.png)

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%208.png)

파일을 어디에 저장할지 지정하는 것 

데이터에서 내가 필요한 row & column 즉, 변수를 지정해준다. 

---

<aside>

### 4. 생성형 AI 및 에이전트 소개

---

Transformer 

**[Encoder-Decoder]**

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%209.png)

### **Transformer의 일반 아키텍처**

Transformer 모델은 크게 두개의 블록으로 구성된다.

### **Encoder (왼쪽)**

- 입력을 받아 입력의 표현(representation) 또는 feature을 만듬.
- Encoder 모델은 입력을 이해하는데 최적화됨

### **Decoder (오른쪽)**

- Encoder의 표현과 Decoder의 입력을 사용하여 target 시퀀스를 생성함.
- Decoder 모델은 출력 생성에 최적화됨

### **Encoder 전용 모델:**

- 입력에 대한 이해가 필요한 task에 사용
- e.g., 문장 분류(sentence classification), 명명된 개체 인식(named entity recognition), 질문 답변(question answering)

### **Decoder 전용 모델**

- 생성 task에 적합함
- e.g., 텍스트 생성(text generation)

### **Encoder-Decoder 모델**

- 입력이 필요한 생성 task에 적합함
- e.g., 번역(translation) 또는 요약(summarization)

# **Encoder 모델**

Encoder 모델은 Transformer의 encoder만 사용하는 모델로 각 stage에 어텐션 레이어가 초기 문장의 모든 단어에 접근할 수 있다. Encoder 모델을 흔히 auto-encoding 모델이라고도 한다.

이 모델을 pre-training하기 위해서는 일반적으로 주어진 문장 중 임의의 단어를 masking 한 후, 모델이 원래 문장을 찾거나 복원하는 작업을 수행하게 한다.

Encoder 모델은 전체 문장의 이해를 요구하는 task에 가장 적합하며 대표적인 Encoder 모델은 다음과 같다.

- ALBERT
- BERT
- DistillBERT
- ELECTRA
- RoBERTa

# **Decoder 모델**

Decoder 모델은 Transformer의 decoder만 사용하며 auto-regressive 모델이라고 부르기도 한다. Decoder 모델의 어텐션 레이어는 각 stage에서 문장 내에서 주어진 단어의 바로 앞 단어만을 접근할 수 있다.

Decoder 모델의 pre-training은 일반적으로 문장의 다음 단어 예측을 중심으로 이루어진다. 따라서 텍스트 생성과 관련 task에 가장 적합하다. 다음은 대표적인 Decoder 모델이다.

- **`GPT`**
- **`GPT-2`**
- Transformer XL

# **Encoder-Decoder 모델**

Encoder-Decoder 모델(또는 Sequence-to-Sequence 모델)은 Transformer의 Encoder와 Decoder를 모두 사용한다. 각 stage에서 encoder의 어텐션 레이어는 초기 문장의 모든 단어에 접근할 수 있는 반면, decoder의 어텐션 레이어는 입력으로 주어진 단어 앞 단어에만 접근할 수 있다.

Encoder-Decoder 모델은 주어진 입력에 따라 새로운 문장을 생성하는 요약, 번역, 생성적 질문 답변에 가장 적합하다. 다음은 대표적인 Encoder-Decoder 모델이다.

- BART
- mBART
- Marian
- T5
- **`출처: [Hugging Face](https://huggingface.co/learn/llm-course/chapter1/1?fw=pt&source=post_page-----a455810193ae---------------------------------------)`**
    
    **0. Setup**
    
    1. Transformer models
    
    2. Using 🤗 Transformers
    
    3. Fine-tuning a pretrained model
    
    4. Sharing models and tokenizers
    
    5. The 🤗 Datasets library
    
    6. The 🤗 Tokenizers library
    
    7. Classical NLP tasks
    
    8. How to ask for help
    
    9. Building and sharing demos
    
    10. Curate high-quality datasets
    
    11. Fine-tune Large Language Models
    
    12. Build Reasoning Models new
    
    Course Events
    

---

</aside>

<aside>

### LLM Model 비교 해주는 사이트

[artificialanalysis.ai](https://artificialanalysis.ai/)

**Artificial Analysis Intelligence Index by Open Weights / Proprietary**

Artificial Analysis Intelligence Index v4.0 incorporates 10 evaluations: GDPval-AA, 𝜏²-Bench Telecom, Terminal-Bench Hard, SciCode, AA-LCR, AA-Omniscience, IFBench, Humanity's Last Exam, GPQA Diamond, CritPt

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%2010.png)

---

### [OpenaiTokenizer](https://platform.openai.com/tokenizer)

token : 의미 단위로 잘라 놓은 것 

token/ized = 토큰이 2개 → LLM을 수행하게 되면 Token을 2개로 인식하게 된다. 

```

```

---

### LLM vs SLM

---

### Azure OpenAI

리소스를 만들려면 해당 페이지로 가야한다. 

단, Open AI에서는 해당 파운트리로 가야한다. 

   → 채팅 플레이 그라운드 

모델 카탈로그 선택하기 

- **Introducing GPT-5.2-codex : 코드에 최적화**
- mini는 SLM을 의미하며 성능적으로는 나쁘지 않으면서 가격은 괜찮은 편

```markdown
### Fine Tuning 
LLM 이나 SLM 에 되도록이면 Fine Tuning을 하지 않는 것이 권고됨 → 필요하다면 최소 1000건 ~ 5000건 필요

단, 지속적으로 변화하는 정보는 Fine tuning을 하지 않는다. 
```

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/45eae9b2-012c-41bc-a4b3-62660ba96bd7.png)

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/ee38f582-1a6a-4006-af61-ae8e11cc3450.png)

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-1/image%2011.png)

**엔드포인트대상 URI**

[https://labuser09openai009.openai.azure.com/openai/deployments/devlabuser09-gpt4.1/chat/completions?api-version=2025-01-01-preview](https://labuser09openai009.openai.azure.com/openai/deployments/devlabuser09-gpt4.1/chat/completions?api-version=2025-01-01-preview)

4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G

```python
1. **API 키를 사용한 인증**
OpenAI API 엔드포인트의 경우 모델을 배포하여 엔드포인트 URL과 API 키를 생성하고, 이를 통해 서비스에 인증합니다. 이 샘플 엔드포인트와 키는 엔드포인트 URL과 API 키를 포함하는 문자열입니다.

모델이 배포되면 배포 + 엔드포인트 페이지에서 API 엔드포인트 URL과 API 키를 찾을 수 있습니다.

API 키를 사용하여 OpenAI SDK로 클라이언트를 만들려면 API 키를 SDK의 구성에 전달하여 클라이언트를 초기화합니다. 이렇게 하면 OpenAI의 서비스와 원활하게 인증하고 상호 작용할 수 있습니다.

import os
from openai import AzureOpenAI

client = AzureOpenAI(
    api_version="2024-12-01-preview",
    azure_endpoint="https://labuser09openai009.openai.azure.com/",
    api_key=subscriptifrom openai import AzureOpenAI

client = AzureOpenAI(
    api_key = "4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G",
    api_version = "2024-12-01-preview",
    azure_endpoint = "https://labuser09openai009.openai.azure.com/"
)

openai=model_name = "gpt-4.1-mini"
openai=deployment = "devlabuser09-gpt4.1"

response = client.chat.completions.create(
    model = "devlabuser09-gpt-4.1",
    messages=[
        {"role":"user",
         "content":"이순신이 누구야?"}
    ]
)

print(response.choices[0].message.content)n_key,
)
```

```markdown
**2. 종속성 설치**

pip install openai

3. 기본 코드 샘플 실행
이 샘플은 채팅 완료 API에 대한 기본 호출을 보여 줍니다. 호출은 동기적입니다.

import os
from openai import AzureOpenAI

endpoint = "https://labuser09openai009.openai.azure.com/"
model_name = "gpt-4.1-mini"
deployment = "devlabuser09-gpt4.1"

subscription_key = "<your-api-key>"
api_version = "2024-12-01-preview"

client = AzureOpenAI(
    api_version=api_version,
    azure_endpoint=endpoint,
    api_key=subscription_key,
)

response = client.chat.completions.create(
    messages=[
        {
            "role": "system",
            "content": "You are a helpful assistant.",
        },
        {
            "role": "user",
            "content": "I am going to Paris, what should I see?",
        }
    ],
    max_completion_tokens=13107,
    temperature=1.0,
    top_p=1.0,
    frequency_penalty=0.0,
    presence_penalty=0.0,
    model=deployment
)

print(response.choices[0].message.content)
```

---

---

```python
**4. 더 많은 샘플 살펴보기**
멀티 턴 대화 실행
이 샘플은 채팅 완료 API를 사용하는 멀티 턴 채팅을 보여 줍니다. 채팅 애플리케이션에 모델을 사용하는 경우 해당 대화의 기록을 관리하고 최신 메시지를 모델로 보내야 합니다.
import os
from openai import AzureOpenAI

endpoint = "https://labuser09openai009.openai.azure.com/"
model_name = "gpt-4.1-mini"
deployment = "devlabuser09-gpt4.1"

subscription_key = "<your-api-key>"
api_version = "2024-12-01-preview"

client = AzureOpenAI(
    api_version=api_version,
    azure_endpoint=endpoint,
    api_key=subscription_key,
)

response = client.chat.completions.create(
    messages=[
        {
            "role": "system",
            "content": "You are a helpful assistant.",
        },
        {
            "role": "user",
            "content": "I am going to Paris, what should I see?",
        },
        {
            "role": "assistant",
            "content": "Paris, the capital of France, is known for its stunning architecture, art museums, historical landmarks, and romantic atmosphere. Here are some of the top attractions to see in Paris:\n\n1. The Eiffel Tower: The iconic Eiffel Tower is one of the most recognizable landmarks in the world and offers breathtaking views of the city.\n2. The Louvre Museum: The Louvre is one of the worlds largest and most famous museums, housing an impressive collection of art and artifacts, including the Mona Lisa.\n3. Notre-Dame Cathedral: This beautiful cathedral is one of the most famous landmarks in Paris and is known for its Gothic architecture and stunning stained glass windows.\n\nThese are just a few of the many attractions that Paris has to offer. With so much to see and do, its no wonder that Paris is one of the most popular tourist destinations in the world.",
        },
        {
            "role": "user",
            "content": "What is so great about #1?",
        }
    ],
    max_completion_tokens=13107,
    temperature=1.0,
    top_p=1.0,
    frequency_penalty=0.0,
    presence_penalty=0.0,
    model=deployment
)

print(response.choices[0].message.content)
```

---

```python
**출력 스트리밍**
사용자 환경 향상을 위해 첫 번째 토큰을 일찍 표시하고 긴 응답을 기다리지 않도록 모델의 응답을 스트림하는 게 좋습니다.
import os
from openai import AzureOpenAI

endpoint = "https://labuser09openai009.openai.azure.com/"
model_name = "gpt-4.1-mini"
deployment = "devlabuser09-gpt4.1"

subscription_key = "<your-api-key>"
api_version = "2024-12-01-preview"

client = AzureOpenAI(
    api_version=api_version,
    azure_endpoint=endpoint,
    api_key=subscription_key,
)

response = client.chat.completions.create(
    stream=True,
    messages=[
        {
            "role": "system",
            "content": "You are a helpful assistant.",
        },
        {
            "role": "user",
            "content": "I am going to Paris, what should I see?",
        }
    ],
    max_completion_tokens=13107,
    temperature=1.0,
    top_p=1.0,
    frequency_penalty=0.0,
    presence_penalty=0.0,
    model=deployment,
)

for update in response:
    if update.choices:
        print(update.choices[0].delta.content or "", end="")

client.close()
```

</aside>

---

```python
from openai import AzureOpenAI

client = AzureOpenAI(
    api_key = "4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G",
    api_version = "2024-12-01-preview",
    azure_endpoint = "https://labuser09openai009.openai.azure.com/"
)

openai=model_name = "gpt-4.1-mini"
openai=deployment = "devlabuser09-gpt4.1"

response = client.chat.completions.create(
    model = "devlabuser09-gpt-4.1",
    messages=[
        {"role":"user",
         "content":"이순신이 누구야?"}
    ]
)

print(response.choices[0].message.content)
```

```python
# 02. AI_poem
import os
from openai import AzureOpenAI 
subscription_key = "4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G"

client = AzureOpenAI(
    api_version="2024-12-01-preview",  # model_name = "gpt-4.1-mini"
    azure_endpoint="https://labuser09openai009.openai.azure.com/",
    api_key=subscription_key,
)

# 기본 코드 샘플 실행
endpoint = "https://labuser09openai009.openai.azure.com/"
model_name = "gpt-4.1-mini"
deployment = "devlabuser09-gpt4.1"

subscription_key = "4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G"
api_version = "2024-12-01-preview"

client = AzureOpenAI(
    api_version=api_version,
    azure_endpoint=endpoint,
    api_key=subscription_key,
)
while True:
    subject = input("시의 주제를 입력하세요: ")
    if subject == "exit":
        break
    content = input("시의 내용을 입력해 주세요")
                
response = client.chat.completions.create(  
    messages=[
    {
        "role":"system",
        "content":"Your are a AI poem",
        },
    {
        "role":"user", 
        "content": "주제는" + subject + "내용은" + content + "로 시를 지어줘",
    }
    ],
    max_completion_tokens=13107,
    temperature=1.0,
    top_p=1.0,
    frequency_penalty=0.0,
    presence_penalty=0.0,
    model=deployment
)  

print(response)

```

```python
# 00. simple Q&A 
import os
# 종속성 설치 : pip install openai
from openai import AzureOpenAI  # temperature = 냉정하거나 감정적이거나 (MBTI의 F or T같은)

# API 키를 사용한 인증
subscription_key = "4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G"

client = AzureOpenAI(
    api_version="2024-12-01-preview",  # model_name = "gpt-4.1-mini"
    azure_endpoint="https://labuser09openai009.openai.azure.com/",
    api_key=subscription_key,
)

# 기본 코드 샘플 실행
endpoint = "https://labuser09openai009.openai.azure.com/"
model_name = "gpt-4.1-mini"
deployment = "devlabuser09-gpt4.1"

subscription_key = "4GVRUxNQg9dXXfuY5rrxmU3ZO5dVpmxVXSfI2zNHQoVYnISIS6kwJQQJ99CBACYeBjFXJ3w3AAABACOG9z4G"
api_version = "2024-12-01-preview"

client = AzureOpenAI(
    api_version=api_version,
    azure_endpoint=endpoint,
    api_key=subscription_key,
)

response = client.chat.completions.create(  
    messages=[  
        {
            "role": "system", 
            "content": "이순신이 누구야?",
            },  
    ],
    max_completion_tokens=13107,
    temperature=1.0,
    top_p=1.0,
    frequency_penalty=0.0,
    presence_penalty=0.0,
    model=deployment
    )  
  
print(response)  
::ChatCompletion(id='chatcmpl-D8LZOXRb1euz1l82C1Z3N0hfKRBwq', choices=[Choice(finish_reason='stop', index=0, logprobs=None, message=ChatCompletionMessage(content=**'이순신(李舜臣)은 조선 시대의 대표적인 군인이자 명장으로, 임진왜란(1592년~1598년) 당시 조선을 침략한 일본군에 맞서 큰 승리를 거둔 장군입니다. 그는 해군 제독으로서 뛰어난 전략과 전술을 사용하여 한산도 대첩, 명량 해전 등 여러 해전에서 일본군을 상대로 결정적인 승리를 거두었으며, 이는 조선의 국토 방어에 큰 기여를 했습니다.\n\n특히 거북선이라는 철갑선을 활용해 해상 전투에서 혁혁한 공을 세운 것으로 유명합니다. 이순신 장군은 충성심과 용맹함, 지도자로서의 능력을 높이 평가받아 조선 역사뿐만 아니라 한국 역사 전반에서 존경받는 인물입니다.**', refusal=None, role='assistant', annotations=[], audio=None, function_call=None, tool_calls=None), content_filter_results={'hate': {'filtered': False, 'severity': 'safe'}, 'protected_material_code': {'filtered': False, 'detected': False}, 'protected_material_text': {'filtered': False, 'detected': False}, 'self_harm': {'filtered': False, 'severity': 'safe'}, 'sexual': {'filtered': False, 'severity': 'safe'}, 'violence': {'filtered': False, 'severity': 'safe'}})], created=1770881910, model='gpt-4.1-mini-2025-04-14', object='chat.completion', service_tier=None, system_fingerprint='fp_3dcd5944f5', usage=CompletionUsage(completion_tokens=191, prompt_tokens=14, total_tokens=205, completion_tokens_details=CompletionTokensDetails(accepted_prediction_tokens=0, audio_tokens=0, reasoning_tokens=0, rejected_prediction_tokens=0), prompt_tokens_details=PromptTokensDetails(audio_tokens=0, cached_tokens=0)), prompt_filter_results=[{'prompt_index': 0, 'content_filter_results': {}}])
```

(AI-900) Microsoft Foundry platform에서 생성 AI 및 에이전트 시작하기 

자연어 처리 개념 소개 

(AI-900) Microsoft Foundry에서 자연어 처리 시작 

AI음성 개념 소개 

(AI-900) Microsoft Foundry에서 음성 시작 

Computer Vision 개념 소개

(AI-900) Microsoft Foundry에서 computer Vision 시작

AI 기반 정보 추출 개념 소개 

(AI-900) Microsoft Microsoft Foundry에서 AI 기반 정보 추출 시작
