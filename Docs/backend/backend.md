# ⚙️ Backend 문서 모음

이 디렉토리는 백엔드 서비스의 구조, API 명세, 배포 방식, 아키텍처 설계 등을 정리한 기술 문서 모음입니다.

---

## 📁 문서 목록

### 1. 📘 [API 명세서](./docs/API_spec.md)
- FastAPI 기반 REST API에 대한 상세 명세
- 경로별 요청 방식, 파라미터, 응답 예시 포함

---

### 2. 🚀 [배포 문서](./docs/deployment.md)
- FastAPI 서버의 실행 및 배포 방법 안내
- 단일 스레드(Uvicorn), 멀티 워커(Gunicorn), Docker 기반 배포 방식 설명
- Nginx 프록시 및 AWS 환경 고려 사항 포함

---

### 3. 🧱 [아키텍처 문서](./docs/architecture/architecture.md)
- 전체 시스템 아키텍처 및 컴포넌트 간 흐름 설명
- 서비스 레이어 구조, 데이터 흐름, 외부 API 연동 방식 시각화

---

### 4. 📝 [README](./backend/README.md)
- `backend/` 디렉토리 구성 설명
- 기술 스택, 폴더 구조, 주요 라이브러리 정리
- 실행 방법 및 테스트 가이드 포함
