# 🌾 팜랜딩 (Farmranding)

> **농장주를 위한 AI 브랜딩 & 가격 제안 플랫폼**  
> 농산물의 브랜드 가치를 높이고 적정 가격을 제안하는 종합 솔루션

![팜랜딩 메인 화면]()
<!-- 여기에 메인 화면 스크린샷을 추가해주세요 -->

---

## 📚 목차

- [🎯 프로젝트 소개](#-프로젝트-소개)
- [✨ 주요 기능](#-주요-기능)
- [🛠 기술 스택](#-기술-스택)
- [📁 프로젝트 구조](#-프로젝트-구조)
- [🚀 설치 및 실행](#-설치-및-실행)
- [📖 API 문서](#-api-문서)
- [🖼 주요 화면](#-주요-화면)
- [💎 멤버십 시스템](#-멤버십-시스템)
- [🐳 Docker 배포](#-docker-배포)

---

## 🎯 프로젝트 소개

**팜랜딩(Farmranding)**은 농장주들이 자신의 농산물에 브랜드 가치를 부여하고, 시장 상황을 고려한 적정 가격을 제안받을 수 있는 AI 기반 플랫폼입니다.

### 🌟 핵심 가치

- **브랜딩**: AI가 농산물 특성을 분석하여 맞춤형 브랜드명과 스토리를 생성
- **가격 제안**: 시장 데이터 기반의 실시간 가격 분석 및 제안
- **전문성**: 농업 전문 도메인에 특화된 서비스
- **접근성**: 농장주 누구나 쉽게 사용할 수 있는 직관적 UI

---

## ✨ 주요 기능

### 🎨 AI 브랜딩
- **브랜드명 생성**: 농산물 특성, 재배 지역, 농법 등을 고려한 맞춤형 브랜드명
- **브랜드 스토리**: 농장의 역사와 가치를 담은 감동적인 브랜드 스토리 (프리미엄 플러스)
- **키워드 분석**: 농산물과 농장의 핵심 키워드 추출 및 활용
- **갭 인증 연동**: GAP 인증 정보 연동으로 신뢰성 있는 브랜딩

![AI 브랜딩 프로세스]()
<!-- 여기에 브랜딩 프로세스 GIF를 추가해주세요 -->

### 💰 스마트 가격 제안
- **실시간 시세**: 가락시장 등 공신력 있는 시장 데이터 기반
- **일반 가격 제안**: 기본적인 시장 가격 분석
- **프리미엄 가격 제안**: 지역별, 품질별 세분화된 가격 분석
- **가격 히스토리**: 과거 가격 제안 내역 관리 및 분석

![가격 제안 시스템]()
<!-- 여기에 가격 제안 화면 스크린샷을 추가해주세요 -->

### 👤 사용자 관리
- **OAuth2 로그인**: 카카오, 구글 간편 로그인
- **프로필 관리**: 농장 정보, 주요 작물 관리
- **사용량 추적**: 기능별 사용 현황 모니터링

### 📊 마이페이지
- **브랜딩 히스토리**: 생성한 브랜딩 프로젝트 관리
- **가격 제안 히스토리**: 과거 가격 제안 내역 조회
- **멤버십 관리**: 요금제 변경 및 사용량 확인

---

## 🛠 기술 스택

### Frontend
- **Framework**: React 19 + TypeScript
- **Build Tool**: Vite 6
- **Styling**: Styled-Components
- **State Management**: React Query (TanStack Query)
- **Routing**: React Router v7
- **Charts**: ECharts
- **UI Development**: Storybook
- **Code Quality**: ESLint + Prettier

### Backend
- **Framework**: Spring Boot 3.5.0
- **Language**: Java 21
- **Database**: MySQL 8.0
- **Authentication**: OAuth2 + JWT
- **Documentation**: SpringDoc OpenAPI 3
- **AI Integration**: Spring AI (OpenAI)
- **Cloud Storage**: AWS S3
- **Container**: Docker + Docker Compose

### Infrastructure
- **Containerization**: Docker
- **Database**: MySQL 8.0
- **External APIs**: 
  - 가락시장 공판장 API
  - 주소 검색 API
  - OpenAI API

---

## 📁 프로젝트 구조

```
farmranding/
├── backend/                    # Spring Boot 백엔드
│   ├── src/main/java/org/fr/farmranding/
│   │   ├── api/               # API 인터페이스
│   │   ├── auth/              # OAuth2 인증
│   │   ├── common/            # 공통 모듈
│   │   ├── config/            # 설정
│   │   ├── controller/        # REST 컨트롤러
│   │   ├── dto/               # 데이터 전송 객체
│   │   ├── entity/            # JPA 엔티티
│   │   ├── repository/        # 데이터 접근 계층
│   │   ├── service/           # 비즈니스 로직
│   │   └── jwt/               # JWT 처리
│   ├── src/main/resources/
│   │   ├── application-*.yml  # 환경별 설정
│   │   └── db/migration/      # DB 마이그레이션
│   └── docker-compose.yml     # 로컬 개발용 DB
├── frontend/                   # React 프론트엔드
│   ├── src/
│   │   ├── api/               # API 서비스
│   │   ├── components/        # React 컴포넌트
│   │   │   ├── common/        # 공통 컴포넌트
│   │   │   ├── branding/      # 브랜딩 관련
│   │   │   ├── pricing/       # 가격 제안 관련
│   │   │   └── layout/        # 레이아웃
│   │   ├── pages/             # 페이지 컴포넌트
│   │   ├── hooks/             # 커스텀 훅
│   │   ├── types/             # TypeScript 타입
│   │   ├── utils/             # 유틸리티
│   │   ├── contexts/          # React Context
│   │   └── stories/           # Storybook 스토리
│   ├── public/                # 정적 파일
│   └── package.json
└── README.md
```

---

## 🚀 설치 및 실행

### 사전 요구사항
- **Java**: 21 이상
- **Node.js**: 18 이상
- **Docker**: 24.0 이상
- **MySQL**: 8.0 (또는 Docker 사용)

### 1. 저장소 클론
```bash
git clone https://github.com/your-username/farmranding.git
cd farmranding
```

### 2. 백엔드 설정 및 실행
```bash
cd backend

# MySQL 데이터베이스 실행 (Docker)
docker-compose up -d

# 환경변수 설정 (application-local.yml 참고)
# JWT_SECRET, OAUTH2 설정, OpenAI API 키 등

# Spring Boot 애플리케이션 실행
./gradlew bootRun
```

### 3. 프론트엔드 설정 및 실행
```bash
cd frontend

# 의존성 설치
npm install

# 개발 서버 실행
npm run dev

# Storybook 실행 (선택사항)
npm run storybook
```

### 4. 접속 확인
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8080
- **Swagger UI**: http://localhost:8080/swagger-ui.html
- **Storybook**: http://localhost:6006

---

## 📖 API 문서

### Swagger UI
개발 서버 실행 후 [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)에서 전체 API 문서를 확인할 수 있습니다.

### 주요 API 엔드포인트

#### 인증
- `POST /api/v1/auth/signup` - 회원가입 완료
- `GET /api/v1/auth/me` - 현재 사용자 정보

#### 브랜딩
- `POST /api/v1/branding/projects` - 브랜딩 프로젝트 생성
- `GET /api/v1/branding/projects` - 브랜딩 프로젝트 목록
- `POST /api/v1/branding/brand-name` - 브랜드명 생성

#### 가격 제안
- `POST /api/v1/price-quotes` - 가격 제안 요청
- `GET /api/v1/price-quotes` - 가격 제안 히스토리
- `POST /api/v1/premium-pricing` - 프리미엄 가격 제안

#### 사용자
- `GET /api/v1/users/profile` - 사용자 프로필
- `PUT /api/v1/users/profile` - 프로필 수정
- `GET /api/v1/users/usage` - 사용량 조회

---

## 🖼 주요 화면

### 🏠 홈 화면
사용자의 첫 인상을 결정하는 랜딩 페이지

![홈 화면]()
<!-- 여기에 홈 화면 스크린샷을 추가해주세요 -->

### 🎨 브랜딩 플로우
단계별 브랜딩 프로세스 진행 화면

![브랜딩 플로우]()
<!-- 여기에 브랜딩 플로우 GIF를 추가해주세요 -->

**브랜딩 단계:**
1. **기본 정보 입력**: 농산물명, 재배지역, 농법 등
2. **키워드 선택**: AI가 제안하는 키워드 중 선택
3. **GAP 인증 확인**: 인증 정보 연동 (선택사항)
4. **브랜드명 생성**: AI 기반 맞춤형 브랜드명 생성
5. **결과 확인**: 최종 브랜딩 결과 및 스토리

### 💰 가격 제안 플로우
시장 데이터 기반 가격 분석 화면

![가격 제안 플로우]()
<!-- 여기에 가격 제안 플로우 스크린샷을 추가해주세요 -->

**가격 제안 단계:**
1. **상품 정보 입력**: 농산물, 품종, 등급 선택
2. **출하 예정일 설정**: 판매 예정 시기
3. **가격 분석**: AI 기반 실시간 가격 제안
4. **결과 확인**: 추천 가격 및 시장 분석

### 👤 마이페이지
개인화된 사용자 대시보드

![마이페이지]()
<!-- 여기에 마이페이지 스크린샷을 추가해주세요 -->

**주요 탭:**
- **브랜딩 히스토리**: 생성한 브랜딩 프로젝트 관리
- **가격 제안 히스토리**: 과거 가격 제안 내역
- **개인정보**: 프로필 및 농장 정보 관리
- **멤버십**: 요금제 및 사용량 현황

---

## 💎 멤버십 시스템

### 🛡 일반 회원 (무료)
- **브랜딩**: 최초 5회 무료
- **가격 제안**: 최초 5회 무료
- **브랜드 스토리**: ❌
- **프리미엄 가격 제안**: ❌

### 🚀 프리미엄 (₩4,900/월)
- **브랜딩**: 무제한 ✅
- **가격 제안**: 무제한 ✅
- **브랜드 스토리**: ❌
- **프리미엄 가격 제안**: ✅

### 💎 프리미엄 플러스 (₩8,900/월)
- **브랜딩**: 무제한 ✅
- **가격 제안**: 무제한 ✅
- **브랜드 스토리**: ✅
- **프리미엄 가격 제안**: ✅
- **판매글 생성**: ✅

![멤버십 비교]()
<!-- 여기에 멤버십 비교 화면 스크린샷을 추가해주세요 -->

---

## 🐳 Docker 배포

### 개발 환경 (MySQL만)
```bash
cd backend
docker-compose up -d
```

### 전체 애플리케이션 배포
```bash
# 백엔드 Docker 이미지 빌드
cd backend
docker build -t farmranding-backend .

# 프론트엔드 빌드 및 배포
cd frontend
npm run build

# 전체 스택 실행 (docker-compose 설정 필요)
docker-compose -f docker-compose.prod.yml up -d
```

### 환경변수 설정
```bash
# .env 파일 생성
JWT_SECRET=your-jwt-secret-key
KAKAO_CLIENT_ID=your-kakao-client-id
KAKAO_CLIENT_SECRET=your-kakao-client-secret
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
OPENAI_API_KEY=your-openai-api-key
AWS_ACCESS_KEY_ID=your-aws-access-key
AWS_SECRET_ACCESS_KEY=your-aws-secret-key
```

---

<div align="center">
  <strong>🌾 농업의 미래를 함께 만들어갑니다 🌾</strong>
</div> 
