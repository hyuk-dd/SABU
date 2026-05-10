<h1 align="center">
  
  ![image](https://github.com/user-attachments/assets/0888af51-a82c-439e-a5c1-4f85326e6a35)
  
</h1>

# SABU (Sell And BUy)

**SABU**는 ETF 및 주식 기반 포트폴리오 전략을 추천하고, 시뮬레이션 및 백테스트를 통해 투자 전략을 분석할 수 있는 **웹 기반 투자 분석 플랫폼**입니다.

---

## 📦 프로젝트 구조

본 프로젝트는 프론트엔드와 백엔드가 하나의 레포지토리 안에 구성된 모노레포(Monorepo) 형태입니다.

| 디렉토리 | 설명 | 바로가기 |
|------------|------|------|
| **`frontend/`** | 사용자 UI 대시보드 (React 기반) | [Frontend 이동](./frontend) |
| **`backend/`** | 백엔드 서버 및 투자 시뮬레이션 API (FastAPI) | [Backend 이동](./backend) |
| **`docs/`** | 프로젝트 아키텍처 및 API 명세 등 각종 문서 | [Docs 이동](./docs) |

---

## ✅ 실행 전 사전 준비 사항

- 백엔드 실행 전, `backend/data/stock` 디렉토리에 **주식 정보 CSV 파일**을 넣어야 합니다.
- 데이터는 **Tiingo API**에서 받은 형식을 따라야 하며, 아래는 예시입니다:

```csv
# {ticker}.csv
date,close,high,low,open,volume,adjClose,adjHigh,adjLow,adjOpen,adjVolume,divCash,splitFactor
2020-09-09,25.0699,25.119,25.0699,25.1,17327,20.8985,20.9395,20.8985,20.9236,17327,0.0,1.0
...
```

- 해당 주식 데이터는 `backend/collect/tiingo_api` 경로의 스크립트를 이용해 자동 수집할 수 있습니다.  

- `.env` 또는 환경변수에 [**Tiingo API 토큰**](https://www.tiingo.com/)을 지정해야 합니다:
```
TIINGO_TOKEN=your_actual_token_here
```
# 시작하기
- 먼저 터미널을 열고 전체 프로젝트를 클론합니다.
```bash
git clone https://github.com/hyuk-dd/SABU.git
cd SABU
```

## 💻 프론트엔드 실행 방법 (React)

```bash
# 1. 프론트엔드 디렉토리로 이동
cd Frontend

# 2. 의존성 설치
npm install

# 3. 로컬 서버 실행
npm run dev
# 또는
npm start
```

## 🐍 백엔드 실행 방법 (FastAPI)
```bash
# 1. 백엔드 디렉토리로 이동
cd Backend

# 2. 가상환경 생성 및 활성화
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# 3. 의존성 설치
pip install -r requirements.txt

# 4. 환경변수 설정 (.env 또는 export)
export TIINGO_TOKEN=your_actual_token_here

# 5. API 서버 실행
uvicorn main:app --host 0.0.0.0 --port 8000

```

> Swagger UI는 http://localhost:8000/docs 에서 확인할 수 있습니다.

## 기능 미리보기

### 🔍 티커 기반 종목 검색
![메인 화면](https://github.com/user-attachments/assets/a18e21f4-e752-43e1-9238-d0d10b561a85)

---

### 🏆 리더보드
![리더보드](https://github.com/user-attachments/assets/b684bfd4-b9ab-4097-b777-392c76d74a23)

---

### 🧠 포트폴리오 추천
![종목 추천](https://github.com/user-attachments/assets/61701a1e-4a3e-42e1-8a2d-56b9aed0a885)

---

### 📈 주가 정보 시각화 제공
![그래프](https://github.com/user-attachments/assets/97f2408c-5446-4980-a04b-170c53077e22)

---

### 📰 뉴스 감정 분석
![감정분석](https://github.com/user-attachments/assets/9ca53201-c521-4ef5-a208-81f314d256f6)

---

### 📊 자동 클러스터링
![클러스터링](https://github.com/user-attachments/assets/d5430a05-3bb5-4ecb-a5e3-7e1a99fcb114)

---

### 🧪 전략 백테스트
![백테스팅](https://github.com/user-attachments/assets/18d02849-3e00-4fff-b017-9800960fb7dc)

---
