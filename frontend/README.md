# Frontend (React)

이 디렉토리는 SABU 프로젝트에서 사용자 인터페이스(UI)를 담당하는 **프론트엔드 애플리케이션**입니다.  
React 기반으로 개발되었으며, REST API를 통해 백엔드와 통신합니다.

> gh-pages로 현재 배포가 되어 [배포 링크](https://hyuk-dd.github.io/SABU/)로 언제든지 접속이 가능합니다. 다만, 프론트엔드와 연결되는 백엔드가 성능상의 이유로 로컬 호스트로 프록스 하는 방식으로 배포되어 있기 때문에 현재 정상적인 내용을 확인할 수 없습니다. 관련 내용은 [기능 시연 이미지](https://hyuk-dd.github.io/SABU) 혹은 직접 배포를 따라하여 보시길 바랍니다. 배포와 관련된 이야기는 [백엔드 배포 문서](../backend/docs/deployment.md)에서 확인하실 수 있습니다.

## 🌐 주요 기능

- 프로젝트/서비스 대시보드
- 시각화 컴포넌트
- 반응형 인터페이스

## ⚙️ 기술 스택

- React + Vite
- useContext 상태 관리
- TailwindCSS
- Axios

## 📁 폴더 구조

```bash
📦 frontend/
 ┣ 📂 docs/                     # 화면 설계 문서, 컨벤션 등
 ┃ ┣ 📂 capture/
 ┃ ┣ 📂 wireframe/
 ┃ ┣ 📜 ui-design.md
 ┃ ┣ 📜 component-guide.md    
 ┃ ┣ 📜 state-flow.md
 ┃ ┣ 📜 Code-Convention.md
 ┃ ┣ 📜 Commit-Message-Convention.md
 ┃ ┣ 📜 Issue-Convention.md
 ┃ ┗ 📜 flow-chart.png
 ┣ 📂 src/
 ┃ ┣ 📂 src/
 ┃ ┃ ┣ 📂 api/                 # API 호출 관련 함수
 ┃ ┃ ┣ 📂 components/          # 재사용 가능한 컴포넌트
 ┃ ┃ ┣ 📂 contexts/            # 전역 상태 관리 컨텍스트
 ┃ ┃ ┣ 📂 pages/               # 페이지 컴포넌트
 ┃ ┃ ┣ 📂 public/
 ┃ ┃ ┣ 📜 App.jsx              # 루트 컴포넌트
 ┃ ┃ ┣ 📜 index.css            # 전역 스타일
 ┃ ┃ ┣ 📜 Layout.jsx           # 레이아웃 컴포넌트
 ┃ ┃ ┣ 📜 main.jsx             # 엔트리 포인트
 ┃ ┣ 📜 eslint.config.js
 ┃ ┣ 📜 index.html
 ┃ ┣ 📜 package-lock.json
 ┃ ┣ 📜 package.json
 ┃ ┗ 📜 vite.config.js
 ┗ 📜 README.md
```

## 📂 `docs/` 폴더 내 문서 목록

- 🧭 **[ui-design.md](./docs/ui-design.md)**  
  와이어프레임 이미지 및 주요 화면 흐름에 대한 설명을 포함합니다.

- 🧩 **[component-guide.md](./docs/component-guide.md)**  
  주요 UI 컴포넌트들의 역할, props 구조, 사용 위치 등을 정리한 문서입니다.

- 🔄 **[state-flow.md](./docs/state-flow.md)**  
  UseContext기반의 상태 관리 구조와 흐름도를 설명합니다.


## 🛠️ 빌드 및 실행 방법

```bash
# 의존성 설치
npm install

# 개발 서버 실행 (http://localhost:5173)
npm run dev

# 프로덕션 빌드
npm run build

# 빌드 결과 미리보기
npm run preview

# 배포 (gh-pages 기준)
npm run deploy
```

---

### 📦 사용 버전 및 환경

| 항목                  | 버전         |
|---------------------|--------------|
| Node.js             | `>=18.x`     |
| npm                 | `>=9.x`      |
| React               | `19.1.0`     |
| Vite                | `6.3.5`      |
| Tailwind CSS        | `4.1.7`      |
| Axios               | `1.9.0`      |
| Chart.js            | `4.4.9`      |
| React Router DOM    | `7.6.0`      |

> ⚠️ 위 버전은 실제 `package.json` 기준입니다. 로컬에서 동일한 버전으로 맞추는 것을 권장합니다.

---

### 🔧 주요 npm 스크립트

| 명령어            | 설명                            |
|------------------|---------------------------------|
| `npm run dev`    | 개발 서버 실행 (`localhost:5173`) |
| `npm run build`  | 프로덕션 빌드 생성 (`dist/`)     |
| `npm run preview`| 빌드 결과 미리보기               |
| `npm run lint`   | ESLint 검사                      |
| `npm run deploy` | gh-pages를 통한 정적 배포         |

---

### 🌐 환경 변수 (.env)

- REST API 엔드포인트는 개발 및 배포 환경에 맞게 설정하세요.
- 해당 값은 `src/api/axiosInstance.js`에서 다음과 같이 사용됩니다:

```js
// src/api/axiosInstance.js
import axios from 'axios';

const axiosInstance = axios.create({
  baseURL: "YOUR_URL", // ✅ 이 부분을 수정하세요
  timeout: 10000,
  headers: {
    'Content-Type': 'application/json',
  },
});

export default axiosInstance;
```
