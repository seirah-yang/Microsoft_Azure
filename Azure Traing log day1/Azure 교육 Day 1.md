# Azure 교육 Day 1

구조 전체트리: TDH Workspace
├─ Dashboard
├─ Daily Ops (DB)
├─ Projects (DB)
├─ Decision Log (DB)
├─ Documents (DB)
└─ Knowledge Library (DB)

1. portforwording_코드: [ ]  Notion DB 5개 생성
[ ]  Obsidian Vault 생성
[ ]  이번 주 프로젝트 1개만 적용
[ ]  Decision 3개 이상 기록
오류 발생 시 해결방법: 동일한 사고 구조를 유지 + Notion은 운영·협업, Obsidian은 사고·축적에 특화

<aside>

### 설계 원칙

1. Daily / Project / Knowledge 3-Layer 고정
2. 결정(Decision)이 모든 기록의 중심
3. 보고·문서로 바로 전환 가능해야 함
4. 마찰 최소화(5분 기록 가능)
</aside>

<aside>

### 🧭 1. Dashboard (실행 중심)

🔹 DP-900 [(Microsoft 업로드 자료)](https://learn.microsoft.com/ko-kr/credentials/certifications/azure-data-fundamentals/?practice-assessment-type=certification): 일본어로 나오면 ko-kr

🔹관계형 / 비관계형 / 데이터 분석 소개 

🔹관련 자격증(59$) 문제 샌드박스 제공 

🔹

</aside>

<aside>

### 🗓️ 2. 데이터의 기본사항/기본개념 살펴보기

---

### **[ 데이터의 구조 ]**

**목적:** 

데이터란  정보를 기록하는데 사용되는 값

데이터 형식 식별하기 

- 구조적: table (sql, progrelsql, mariadb)
- 반구조적: No-SQL (json, csv, html)
- 비구조적: file형태로 저장되는 Stoage를 사용함
    
    → Azure에서 어떤 서비스를 불러와서 사용할 것인가?
    

`정형데이터`

---

### **[DekunutedText]**

**Json(Javascript Object Notation)**

(

  ”customers”:

[

{

}]

  )

**XML(Extensible Markup Language)** 

<Customer firstNmae = “Joe” LastName=”Jones”/>

**BLOB(Binary Large Object)**

블롭, 블롭 컨테이너 

10110101101010110010… 

**최적화된 형식** 

Avro, ORC, Parquet

---

### [Database]

**Related**

관계에 따라 물리적으로 검증이 가능한 경우가 발생 

→ 이 것의 장점을 살려서 쓸 수 있음

SQL query → DB가 나의 질문을 해석 → 내가 필요한 정보 도출 

**Non-Related** 

Key - value : 

Documnet DB = table 안에 굳이 Json을 넣는다. 

Orders: table storage ( column Family) 

No-SQL 각각의 데이터간의 관계X → 속도가 유지 

→ 모두 Vector 형태로도 지원이 가능하다 

---

### [운영 데이터 워크로드]

**OLTP (Online Transaction Process)**

- 동시성의 오류
- 스노우플레이크 & Hazelcaset
- **`초당 몇개의 Transaction을 처리할 수 있다가 중요한 포인트`**가 된다.

<aside>

**트랜잭션은 “ACID”기반이다**. 

원자성

일관성

격리

내구성 

</aside>

---

### [분석데이터 워크로드]

1. 작동데이터가 분석을 위해 데이터 레이크로 추출하고 변환 및 로드 (ETL)된다. 
2. 데이터가 테이블 스키마로 로드 되고, 일반적으로 데이터 레이크의 파일에 대한 테이블 형식 추상화가 있는 Spark기반 데이터 레이크하우스 또는 완전 관계형 SQL 엔진이 있는 데이터 웨어하우스에서 로드 됩니다. 
3. 테이블의 데이터는 집계하여 OLAP(온라인 분석처리) **모델 큐브**에
4. 

→ 이것에 따라 Azure 서비스 선택이 달라진다. 

---

데이터를 **계층적으로 연결해 놓은 것을 소셜 네트워크 연결 분석** 

→ 

ex) 팔란티어 / Godam / Gremlin

---

</aside>

<aside>

### Azure data analysis

[Microsoft Datacenter](https://datacenters.microsoft.com/globe/explore/datacenter/)

전세계가 광케이블로 연결되어 있어서 모든 Resion filter 사용 가능 

East/West 400$/month

**Sweden** (GPU parm Good) 420~430$/month

→ 최신 AI 자원이 잘 들어오니 여기 것 쓰는 것 추천

단, **`이스라엘, 중국, 독일`** Region filter는 사용 자제 

---

- 작업: portal (=console)
    - 하나의 테넌트
    - 테넌트 아래 아이디들을 모아 놓은 상태 (labuser 1~99)
    - labuser16@helloaicloud.onmicrosoft.com
    → Hands on Lab (구독 설정 +)
        
        !Seoul2026
        

Owner / **`contributer`**권한 

### Decisions

- labuser1-rg (리소스그룹에 끝에 rg를 붙이는 관행이 있어)
- 외부 유출이 되면 안되는 정보들은 되도록 한국 central, south 지역 두 군데에만 만들고 막아 놓는다.
</aside>

```markdown
### Tomorrow
### Project 메인 템플릿
### 클라우드 OS

- 목적: 살려도 주고 죽이기도 하고, 관리해주고 Terminal 
- 핵심 endpoint:
- TDH 범위:

### Open Issues
### Next Milestone

```

![image.png](image.png)

```markdown
### 서버이름 : labuser16-mysql-0016
### 지역 선택 : 뉴질랜드
### 워크로드 유형 : 개발/테스트
### 고가용성: 고가용성은 장애 발생 시 서버의 복원력을 높여줍니다. '컴퓨팅 + 스토리지 '에서 고가용성 옵션을 지정할 수도 있음
   = **사용 안 함(99.9% SLA)**
### 가용성 영역: 기본 설정 없음

배포 이름
:MySqlFlexibleServer_2944aae99e424d919c14f30c64532966
구독
:Hands on lab
리소스 그룹
:labuser16-rg
시작 시간
: 2026. 2. 11. 오전 11:42:40
상관 관계 ID
: d8a229ad-145a-4ac5-9907-eddac28ec59d

**제품 정보: Azure Database for MySQL** 
구독: Hands on lab
리소스 그룹: labuser16-rg
서버 이름: labuser16-mysql-016
관리자 로그인: seirah
MySQL 버전: 8.0
  컴퓨팅 + 스토리지 버스트 가능, B1ms, 1 vCore, 2 GiB RAM, 
  20 스토리지, 자동 크기 조정 IOPS
백업 보존 기간(일) : 7일
스토리지 자동 증가 : 사용
지역 중복: 사용 안 함
영역 복원력 : 아니요
네트워킹 (변경) :
연결 방법: 공용 액세스(허용된 IP 주소) 및 프라이빗 엔드포인트
공용 IP 주소를 사용하여 인터넷을 통해 이 리소스에 공용 액세스 허용: 예
Azure 내의 모든 Azure 서비스의 이 서버에 대한 퍼블릭 액세스 허용: 아니요
**방화벽 규칙 : x -> 추후 등록** 
SSL/TLS: SSL이 시행되고 TLS 버전은 1.2입니다. 서버 생성 후 변경할 수 있습니다. 

**자세한 정보** 
추가 구성 (변경)
데이터 암호화: 서비스 관리형 키
서버 매개 변수 - lower_case_table_names: 1
태그 (변경)
예상 비용: 컴퓨팅 - USD 16.06/월
Standard_B1ms (1 vCore): 16.06
스토리지: USD 2.76/월
					20GiB (GiB당 USD 0.14) 20 x 0.14
자동 확장 IOPS
자동 크기 조정 IOPS는 백만 개의 요청 증분 단위로 사용량에 따라 청구됩니다. 
백업 보존
백업 보존은 백업 보존에 사용되는 추가 스토리지를 기준으로 청구됩니다.
대역폭
다양한 지역의 서비스 간에 아웃바운드 데이터 전송에는 추가 요금이 발생합니다. 모든 인바운드 데이터 전송은 무료입니다. 
```

---

![image.png](image%201.png)

---

**Database Admin → Database Manager**

- 데이터베이스 프로비저닝, 구성, 관리
- 데이터 베이스 보안 및 사용자 액세스
- 복원력
- 모니터링

**데이터 엔지니어** 

- 데이터 통합 파이프라인 및 ETL 프로세스
- 데이터 정리 및 변환
- 분석 데이터 저장소 **스키마 및 데이터 로드**`(큐브와 같은 역할)`

**데이터분석가** 

분석 모델링 

데이터 보고 및 요약

데이터시각화 

→ `Power BI (데이터 엔지니어에게 요청해서 받아오는 경우가 많음)`

ex) Store Sales Overview

---

**Paas**

Azure Data Bricks

Microsoft Purview: 
엔터프라이즈 전체 데이터 거버넌스 및 검색 가능성을 위한 솔루션 

---

### Azure의 관계형 데이터의 기본사항 살펴보기

1. MySQL Workbench download 및 설치하기 
2. **MySQL Connection 추가하기**
    
    ![image.png](image%202.png)
    
    **Connection Name**: DP-900
    
    **Connection method** : Standard(TCP/IP)
    
    hostnme = MySQL hostnme 입력 (=Azure의 엔드포인트) 
    
    User name = 내 아이디 (Azure 만들때 썼던 것)
    
    password는 내가 MySQL에서 새로 만들게 됨 
    
    port = 3306
    
3. Azure page에서 왼쪽 활동 로그 

![image.png](32475204-e66f-49a9-92d6-fd7469e9dbec.png)

![image.png](32475204-e66f-49a9-92d6-fd7469e9dbec.png)

 → 리소스 시각화 도우미 > 설정 → 방화벽 규칙 이름(DevPC_016)/시작IP주소/종료 IP주소 

→ Work Bench에서 다시 Connect 시도 

---

[MySQL Tutorial](https://www.mysqltutorial.org/) : 샘플 데이터베이스 다운로드 받을 수 있는 사이트

 

![image.png](image%203.png)

 다운로드 zip파일 받아서 압축 풀기 → (query들의 모음) 파일 가져오기 
→ 파일을 불러오면 코드가 입력됨 

![image.png](image%204.png)

**번개필터 눌러서 실행 → 1번 → 2번 → 3번** 

![image.png](image%205.png)

---

### 표준화 / 정규화

- SQL은 관계형 DB에 사용하기 위한 표준 언어
- 표준은 ANSI 및 ISO에 의해 유지 관리된다.
- 대부분의 RDBMS 시스템은 표준 SQL 독점 확장을 지원한다.
    - T-SQL
    - PL-SQL
    - ANSI-SQL
- **DML (데이터 조작 언어) - Data CRUD** 
data Insert, Update, Delete, Select
- DDL :
- DCL : 데이터 권한을 컨트롤

`각각의 개념 **` 

---

### 기타 일반적인 데이터베이스 개체

- **뷰**: 가상 테이블로 작동하는 미리 정의된 SQL 쿼리
    
    데이터 전체에 접근은 되지 않고 일정 부분만 볼 수 있도록 “뷰”로 권한을 제한한다.  
    
- **저장 프로시저** : 매개 변수를 포함할 수 있는 미리 정의된 SQL 문
- **인덱스** : 쿼리 성능을 향상시키는 트리 기반 구조
    - 
    - 
    - Azure SQL DB

---

<aside>

## 3. **Azure SQL**

**성능, 용량 및 비용을 최적화하는 데이터베이스 옵션을 제공**

서버 하나를 만들고 여러개의 DB를 여러가 안에 만들어 두는 것이 가능하다. 

---

### [오픈소스를 위한 Azure SQL Database 만들기]

**서버이름** : 어렵게 

**위치** : 이전 것과 똑같이 (뉴질랜드)

**인증방법** : SQL 인증 사용 

**서버 관리자 로그인** : 아이디 

**패스워드:**

**엘라스틱 풀 =** 아니오

**워크로드 환경** = 개발 

**컴퓨팅 스토리지** = 범용 서버리스 (표준 시리즈)

**백업스토리지 중복**: 로컬 중복 백업스토리지 

![image.png](image%206.png)

**`<네트워킹>`**

네트워크연결 

**연결방법** = 엑세스 권한 없음 또는 프라이빗 엔드포인트 

** **퍼블릭 엔드포인트로 하게 되면Azure 안에서 접속이 가능**하게 되고, 

지금 IP와 같은 IP를 같이 사용하고 있는 다른 PC 가 해당 데이터에 접근이 가능해진다. 

**`<보안>`**

**Microsoft Defender for SQL** 

- Azure Ddos 방어용 → 일반적으로 Azure 안에서는 Ddos basic version을 실행함
- 유료용은 pattern을 학습해서 더 강화용으로 Deffend

**`<추가설정>`**

기존 데이터 사용 = 없음 

데이터 정렬 = 기본 설정 default값으로 

유지 관리 기관 = 일괄시간(시스템 기본값으로 설정하는게 Best)

---

## [Tool]

- Microsoft SQL Management : Window만 제공
- Azure Data Studio : windows, McOS, Linux 모두 제공
</aside>

---

- Snowflake/Hazelcast/OLTP
    
    <aside>
    
    > “ACID 기반 OLTP 트랜잭션 요구사항은 Snowflake와 Hazelcast 모두와 ‘관련’은 있지만,
    두 플랫폼이 담당하는 ACID의 범위와 책임은 다릅니다.”
    > 
    
    ---
    
    ### 1️⃣ OLTP에서 말하는 “ACID”는 무엇을 전제로 하는가
    
             OLTP 맥락에서의 트랜잭션은 **전통적 RDBMS 기준**입니다.
    
    | ACID | 의미 | OLTP에서의 기대 |
    | --- | --- | --- |
    | Atomicity | 전부 성공 or 전부 실패 | 금융/결제 필수 |
    | Consistency | 규칙 위반 없음 | 제약조건 유지 |
    | Isolation | 동시 트랜잭션 간 간섭 없음 | Lock / MVCC |
    | Durability | 커밋 후 영구 보존 | Disk 기반 |
    
    👉 이 ACID는 “단일 DB에서의 트랜잭션 처리”를 전제로 합니다.
    
    ---
    
    ## 2️⃣ Snowflake와 ACID의 관계
    
    ### ❓ Snowflake는 ACID를 지원하는가?
    
    ➡️ **예, 하지만 목적이 다릅니다.**
    
    Snowflake의 ACID 특성:
    
    - ✔ **ACID-compliant**
    - ✔ MVCC 기반 Isolation
    - ✔ 트랜잭션 일관성 보장
    - ❌ **고 TPS OLTP용 아님**
    
    ### Snowflake의 본질
    
    - **OLAP (Analytical Processing)**
    - 대용량 데이터
    - 동시 쿼리
    - 초당 수천 TPS ❌
    - **“초당 몇 개 트랜잭션”은 Snowflake의 KPI가 아님**
    
    👉 Snowflake에서의 ACID는
    “분석 중 데이터 일관성 보장”을 위한 ACID입니다.
    
    ---
    
    ## 3️⃣ Hazelcast와 ACID의 관계 (핵심)
    
    Hazelcast는 **전통적 RDBMS형 ACID 트랜잭션 엔진이 아닙니다.**
    
    ### Hazelcast의 트랜잭션 모델은 **분리되어 있음**
    
    ### 1) 기본 데이터 구조 (IMDG 영역)
    
    - IMap, Cache 등
    - ❌ Full ACID 아님
    - ✔ Eventually Consistent (AP 중심)
    - ✔ **고 TPS / 저지연**
    
    ➡️ 여기서 중요한 KPI:
    
    > **“초당 몇 개의 트랜잭션을 처리할 수 있는가”**
    > 
    
    즉, 질문에 나온 문장:
    
    > **`초당 몇개의 Transaction을 처리할 수 있다`**
    > 
    
    ➡️ **Hazelcast 쪽에 훨씬 더 직접적으로 연결된 포인트**입니다.
    
    ---
    
    ### 2) CP Subsystem (Raft 기반)
    
    Hazelcast는 **의도적으로** ACID 영역을 분리합니다.
    
    | 영역 | 성격 |
    | --- | --- |
    | AP 영역 | 성능 / 확장성 |
    | CP 영역 | 강한 일관성 |
    
    CP Subsystem:
    
    - ✔ Linearizable consistency
    - ✔ Raft consensus
    - ✔ Atomic operations
    - ❌ 고 TPS에는 부적합
    
    👉 **“모든 데이터를 ACID로 만들지 않는다”**
    👉 **필요한 부분만 ACID로 만든다**
    
    ---
    
    ## 4️⃣ “초당 몇 개 트랜잭션”이라는 문장은 누구의 관점인가
    
    이 문장은 **전통 OLTP DB 관점**에서 온 질문입니다.
    
    | 플랫폼 | 이 질문의 중요도 |
    | --- | --- |
    | RDBMS (MySQL, Oracle) | 🔥 매우 중요 |
    | Hazelcast | 🔥 중요 (In-memory TPS) |
    | Snowflake | ❌ 거의 의미 없음 |
    
    왜냐하면:
    
    - Snowflake는 **OLTP 시스템이 아니기 때문**
    - Snowflake는 **transaction volume이 아니라 scan volume**이 중요
    
    ---
    
    ### 5️⃣ Snowflake + Hazelcast 조합에서 ACID의 역할 분담
    
    ### 전체 그림
    
    ```
    [ OLTP Source DB ]
       (Full ACID)
            ↓
    [ Hazelcast ]
      - High TPS
      - Low latency
      - Partial consistency
            ↓
    [ Snowflake ]
      - Analytical ACID
      - Consistent analytics
    ```
    
    ### 역할 분리 요약
    
    | 역할 | 담당 |
    | --- | --- |
    | 강한 트랜잭션 무결성 | Source DB |
    | 실시간 처리 / 속도 | Hazelcast |
    | 분석 일관성 | Snowflake |
    
    ---
    
    ## 6️⃣ 질문에 대한 답 (명확하게)
    
    > **이 ACID 개념이 지금 Snowflake와 Hazelcast와 관련되어 있는가?**
    > 
    
    ### ✔ 관련은 있다
    
    ### ❌ 하지만 동일한 의미는 아니다
    
    - Snowflake의 ACID → **분석 안정성**
    - Hazelcast의 ACID → **선택적 / 제한적**
    - “초당 몇 개 트랜잭션” → **Hazelcast 중심 지표**
    
    > “OLTP에서 말하는 ACID 트랜잭션을
    Snowflake나 Hazelcast에 그대로 기대하면 안 됩니다.
    > 
    
    > Hazelcast는 트랜잭션 무결성보다 **속도와 상태 처리**를,
    Snowflake는 트랜잭션 처리보다 **분석 일관성**을 책임집니다.”
    > 
    
    ### OLTP 트랜잭션을 “ACID 없이” 정의하면 무엇인가
    
    ACID를 빼고 보면, OLTP 트랜잭션의 핵심은 다음 3가지입니다.
    
    ### OLTP의 본질적 요구 (비-ACID 관점)
    
    1. 높은 동시성
        - 수많은 요청이 동시에 들어옴
    2. 낮은 지연(latency)
        - ms 단위 응답
    3. 높은 처리량(Throughput)
        
        초당 몇 건의 트랜잭션을 처리할 수 있는가 (TPS)
        
    
    👉 즉,
    OLTP = “빠르고, 동시에, 많이 처리하는 것”
    
    ### 이 기준으로 Snowflake는 OLTP와 어떤 관계인가
    
    ## Snowflake의 포지션
    
    ### Snowflake는 OLTP 트랜잭션 플랫폼인가?
    
    - ❌ 아니다
    
    ### 이유 (ACID 제외하고 봐도 명확)
    
    | OLTP 요구 | Snowflake |
    | --- | --- |
    | 높은 TPS | ❌ |
    | ms 단위 latency | ❌ |
    | 지속적 write/update | ❌ |
    | 실시간 상태 변경 | ❌ |
    
    ### Snowflake의 설계 목적
    
    - 대규모 읽기 중심
    - 배치성 insert / merge
    - 분석 쿼리 병렬 처리
    
    👉 Snowflake에서의 “트랜잭션”은
    OLTP 트랜잭션이 아니라 “분석용 데이터 변경 단위”
    
    ### 핵심 정리
    
    > Snowflake는 OLTP 트랜잭션을 “처리”하는 시스템이 아니라
    OLTP 결과를 “분석”하는 시스템이다.
    > 
    - Hazelcast는 OLTP 트랜잭션과 어떤 관계인가
    
    ## Hazelcast의 포지션
    
    Hazelcast는 전통적인 DB는 아니지만,
    OLTP의 “운영적 요구사항”과 가장 가까운 플랫폼
    
    ### OLTP 요구 vs Hazelcast
    
    | OLTP 요구 | Hazelcast |
    | --- | --- |
    | 높은 TPS | ⭕ 매우 강함 |
    | ms 단위 latency | ⭕ In-memory |
    | 동시성 처리 | ⭕ 분산 처리 |
    | 실시간 상태 변경 | ⭕ 핵심 강점 |
    
    ### Hazelcast가 잘하는 것
    
    - 초당 수십만~수백만 이벤트 처리
    - 상태(state) 기반 연산
    - 동시 업데이트
    - 실시간 집계
    
    👉 Hazelcast는
    “OLTP를 대체하는 DB”는 아니지만
    “OLTP 앞/옆에서 실시간으로 트랜잭션을 흡수·처리하는 레이어”
    
    # “초당 몇 개의 트랜잭션”이라는 지표는 누구에게 중요한가
    
    | 플랫폼 | TPS 중요도 |
    | --- | --- |
    | 전통 OLTP DB | 🔥🔥🔥 |
    | Hazelcast | 🔥🔥 |
    | Snowflake | ❌ |
    
    왜냐하면:
    
    - Hazelcast는 **메모리 기반 + 분산**
    - Snowflake는 **스토리지 기반 + 분석 최적화**
    
    👉 따라서 이 문장:
    
    > “초당 몇 개의 트랜잭션을 처리할 수 있는가가 중요한 포인트”
    는
    ➡️ **Hazelcast와 직접적으로 연결되는 문장**
    ➡️ **Snowflake에는 거의 의미 없음**
    > 
    
    # OLTP 트랜잭션 흐름에서의 역할 분담 (ACID 제외)
    
    ### 현실적인 전체 구조
    
    ```
    [ OLTP Source System ]
      (App / API / DB)
            ↓
    [ Hazelcast ]
      - 실시간 처리
      - 고 TPS
      - 상태 유지
            ↓
    [ Snowflake ]
      - 집계 결과 저장
      - 분석 / BI / AI
    ```
    
    ### 각자의 역할
    
    | 계층 | 역할 |
    | --- | --- |
    | OLTP Source | 실제 트랜잭션 발생 |
    | Hazelcast | 트랜잭션 **실시간 처리/집계/판단** |
    | Snowflake | 트랜잭션 **결과 분석** |
    
    ---
    
    # Snowflake vs Hazelcast — OLTP 관점 비교 요약
    
    | 구분 | Hazelcast | Snowflake |
    | --- | --- | --- |
    | OLTP 친화성 | ⭕ | ❌ |
    | 실시간성 | ⭕ | ❌ |
    | TPS 지표 | 중요 | 의미 없음 |
    | 역할 | Operational Processing | Analytical Processing |
    | 데이터 성격 | Hot / Live | Cold / Aggregated |
    
    ---
    
    > “OLTP 트랜잭션 관점에서 보면
    Snowflake는 트랜잭션을 처리하는 시스템이 아니라
    **트랜잭션 결과를 분석하는 시스템**이고,
    Hazelcast는 **트랜잭션이 발생하는 순간을 처리하는 플랫폼**입니다.”
    > 
    
    또는 더 직설적으로:
    
    > “TPS가 중요해지는 순간,
    Snowflake는 무대에서 내려오고
    Hazelcast가 무대에 올라옵니다.”
    > 
    
    ---
    
    # 8️⃣ 한 줄 결론
    
    - OLTP 트랜잭션 ≠ Snowflake
    - OLTP 트랜잭션과 가장 가까운 것은 Hazelcast
    - 둘은 경쟁이 아니라 **시간축이 다른 레이어
    
    다음으로 이어가면 가장 좋은 주제는:
    
    - OLTP → Live Data Platform → OLAP 시간축 구조
    - 왜 Snowflake 앞단에 Hazelcast가 필요한가 (비즈니스 시나리오)
    
    원하시면 바로 이어서 정리해 드릴게요.
    
    ---
    
    </aside>
    

---

<aside>

## 4. Azure Sotrage 기본사항

---

### 비관계형 데이터의 기본사항 살펴보기

**1) Azure Blob Storage**

BLOB으로 데이터에 대한 스토리지 

- `블록 블롭`
- 가장 많이 사용한다. 
- 자주 변경되지 않는 크고 비-연속적인 이진 개체 
- Blob은 최대 4.17TB일 수 있으며 최대 100의 블록으로 구성 됨
    - Blob에는 최대 5만개의 블록이 포함될 수 있다.
- 페이지 블롭
- Vm용 가상 디스크 스토리지로 사용 
- Blob은 최대 8TB일 수 있으며 고정 크기인 512바이트 페이지로 구성된다.
- 추가 블롭 
- 추가 작업을 치적화하는 데 사용 되는 블록Blob
- 최대 크기는 195GB를 초과

**2) 블롭당 스토리지 계층** 

- 핫: 가장 높은 비용. 가장 낮은 대기 시간
- 쿨: 더 낮은 비용, 더 높은 대기 시간
- 보관 : 가장 낮은 비용, 가장 높은 대기 시간
</aside>

<aside>

![image.png](image%207.png)

- 스토리지 계쩡 이름: labuser16storage0016
소문자만 가능, 하이픈 사용 불가
- 지역: 내가 선택 (중국이랑 이스라엘, 독일만 피해라)
- 기본 스토리지 유형 :
- 성능: Azure Blob Storage 또는 Azure Data Lake Storage Gen 2
- 복제: RA-GRS(읽기 액세스 지역 중복 스토리지)
- 중복도
- 상관관계 : 87b68fdb-78bd-4e70-a6a2-54e455a56aca

![image.png](image%208.png)

---

**파일서비스** = NAS

**큐서비스** = 데이터 First in First out & last in Last out 그 Queue

![image.png](image%209.png)

| Key | column의 수는 제각각 |  |
| --- | --- | --- |
| — row → | — row → |  |

![image.png](image%2010.png)

---

![image.png](image%2011.png)

**<컨테이너에서 이미지 업로드 & 불러오기>**

- URL : https:// protocol & 이미지 파일이 부하를 많이 일으킨다. → 개별 storage를 생성해서 다룬다.

**<컨테이너 공개 범위 변경>**

설정 > 구성 > Blob 익명 액세스 허용 사용 

→ 리소스 시각화 도우미 > 데이터 스토리지 > 컨테이너 > 액세스 수준 변경 > Blob 수준에서 허용으로 변경 

→ **image-data** 

![image.png](image%2012.png)

→ 이제 복사해서 https:// 로 붙여 넣으면 이미지가 보이게 됨 

![image.png](image%2013.png)

→ 이때 주소에 Window.net이 들어감 

![image.png](image%2014.png)

</aside>

<aside>

## `2. CosmosDBMS`

Azure Cosmost DB API

1) Azure Cosmos DB for No SQL
Cosmos DB용 네이티브 API = **Document DB 였는데 … 
다른것에 Document DB 네이밍을 주고 Cosmos DB로 re-naming**

2) Azure Cosmos DB for SQL

- MongoDB

3) Azure Cosmos DB for postgreSQL

- PostgreSQL과의 호환성
- 동시성이 좋다.

| **ID** | **name** | **부서**  |
| --- | --- | --- |
|  |  |  |
|  |  |  |

**계층형 데이터** 

**그래프데이터** 

**Gremlin**

</aside>

<aside>

### 데이터 분석의 기본사항 살펴보기

---

 **1)  대규모 데이터 분석** 

① 데이터 수집 및 관리 

② 분석데이터 저장소 

③ 분석 데이터 모델 : 분석 엔터티에대한 의미 체계 모델 

하나 이상의 창에 숫자 값을 

④ 데이터 시각화 : 보고서, 차트, 대시보드 

---

 **2)    대규모 분석에서의 데이터 처리** 

**관계형 데이터베이스** 

- 관계형 데이터 스토리지 및 러리를 위한 잘 정립된 모델
- 쿼리 및 데이터 조작을 위한 포괄적인 SQL 언어 지원

**Apache Spark** 

- 확장 가능한 분산형 데이터 처리를 위한 오픈 소스 플랫폼
- 다중 언어 데이터 처리 코드(파이썬, Scala, Java, SQL)

Data Warehouse

- 데이터는 관계형 데이터베이스에 저장되고 SQL 쿼리 엔진을 사용하여 쿼리된다.
- 쿼리 최적화를 위해 데이터가 비정규화 된다. 
- 일반적으로 차원별로 집계할 수 있는 숫자 팩트의 별 또는 눈송이 스키마

**Date Lakehouse**

**DataBricks를 사용하는 Paas 데이터 분석** 

- Azure Data Factory를 사용하여 데이터 수집 및 처리 파이프라인 구현
- 데이터브릭스 클라우드 분석 플랫폼의 Azure 기반 구현 
cf. Data fabric으로 가게 되면 조금더 많은 정보를 다룰 수 있게 된다.
- 데이터 레이크 분석을 위한 스케일링 가능한 스파크 및 SQL 쿼리
- Azure Databricks 작업 영역의 대화형 환경

**Hadoop = Azure HD insight** 

</aside>

<aside>

스트림 처리의 공통요소 

이벤트에서 일부 데이터를 생성

생성되는 데이터는 ㅊ ㅓ리를 위해 스트리밍 소스에 캡처 

이벤트 데이터가 처리 됨

스트림 처리 작업의 결과는 출력(또는 싱크(에 기록된다. 

**`HTTP/MQTT/ASMQ → Event Hub/IoT Hub → Stream Analysis →`** 

---

Microsoft Fabric의 실시간 분석 

여러 소스로부터 지속적인 데이터 수집지원 

Event stream에서 스트리밍 데이터 캡처

레이크하우스 또는 KQL 데이터 베이스의 테이블에 실시간 데이터 쓰기 

SQL 또는 KQL을 사용하여 실시간 데이터 쿼리 

실시간 데이터 구축 BI

---

Apatche Spark

</aside>

<aside>

## 데이터 시각화

---

- Power BI Desktop으로 시작
    - 하나 이상의 소스에서 데이터 가져오기
    - 데이터 모델 정의
    - 보고서에서 시각화 만들기
- Power BI 서비스에 게시
    - 데이터 새로 고침을 예약
    - 대시보드 및 앱 만들기
    - 다른 사용자와 공유
- 게시된 보고서와 상호작용
    - 웹 브라우저
    - Power BI **휴대폰 앱**

<aside>

**Flow**

엑셀/대시보드/SQL/Cloud/documents/() → Power BI Desktop → Power BI services → web browser/Power BI mobile application 

</aside>

---

[**자습서: Power BI 서비스에서 만들기 시작**](https://learn.microsoft.com/ko-kr/power-bi/fundamentals/service-get-started)

</aside>