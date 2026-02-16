# Azure 교육 Day2-2

구조 전체트리: TDH Workspace
├─ Microsoft Foundry
├─ 에이전트 
├─ Open AI
├─ 클로스 오퍼스 4-1
├─ Kimi K-2.5
└─ Deepseekv3.2

<aside>

### 1. 에이전트

에이전트를 만들 때, 적절한 모델을 사용하기 위해 [여기](https://ai.azure.com/explore/models?tid=373346ec-cc5f-4210-b5bc-9a4c2d9517d8)에서 보고 비교해볼 수 있다. 

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-2/image.png)

</aside>

<aside>

### 2. Azure AI Foundry Model

---

**목적:** 

Foundry Model

Base Model

→ 공장에서 막 나온 모델들 

단, Gemini는 안준다. 

</aside>

---

<aside>

## 3. Azure의 AI소개 : 자연어 생성

---

**1)  [Microsoft 에이전트 프레임워크](https://learn.microsoft.com/ko-kr/agent-framework/overview/agent-framework-overview)**

    → python, $C^ \sharp$ 

---

**Lang-Graph**

**GraphRAG**

**Node**

---

원시 텍스트 → 전처리 → 토큰화 → 학습 → 모델 

TTS<———> STT

</aside>

---

<aside>

### 4. Computer Vision

---

**1) vision service** 

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-2/image%201.png)

```markdown
### Issue

```

---

**2) face 인식** 

```markdown
## Pattern
```

</aside>

![image.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-2/image%202.png)

![labuser09-rg.png](Azure%20%EA%B5%90%EC%9C%A1%20Day2-2/labuser09-rg.png)

---

- Noise remove = ML
- Multimodal LLM을 통한 이상 탐지
- Prompt Engineering
- category별로 에이전트를 각각 다른 것을 만들고 그것을 마지막으로 슈퍼 에이전트로 정리
- LLM을 통한 업무 자동화
- 사내 데이터 조회 챗봇 활용 사례 
 → Resut & insight 
GEN AI
- 판례에 대한 내용을 사내문서로 만들기 위해서 자체 chatbot을 만들기 위해서 RAG 를 만드는데
- Azure 안에서 보안이 가능하기 때문에 GPT 사용이 가능함
- RAG DB 판례를 받아서 지속적으로 업데이트