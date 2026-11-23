 
<div align="center">

# 📍 Meetdle

### 우리 사이, 가장 좋은 만남의 지점

**여러 사람의 출발지를 연결하고, 함께 만날 장소를 결정하는 서비스**

<br>

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![SCSS](https://img.shields.io/badge/SCSS-CC6699?style=for-the-badge&logo=sass&logoColor=white)

<br>

**LIKELION 4호선톤 | TEAM 20**

[Repository](https://github.com/LIKELION-4THON-TEAM20/Meetdle_FE) · [Convention](CONVENTION.md)

</div>

---

## 💜 About Meetdle

> **"어디서 만나는 게 좋을까?"**
>
> 서로 다른 위치에서 출발하는 사람들이 더 편리하게 만날 수 있도록.

**Meetdle**은 여러 사람의 출발지를 기반으로 중간 지점을 탐색하고, 약속 장소를 함께 결정하는 웹 서비스입니다.

약속방 생성부터 일정 조율, 장소 후보 등록, 투표, 최종 장소 확정까지 하나의 흐름으로 연결합니다.

React, TypeScript, Vite를 기반으로 구현하였으며, 실제 백엔드 API와 연동하여 약속방 및 장소 데이터를 관리합니다.

<br>

## ✨ Key Features

| 기능 | 설명 |
|:---:|---|
| 🔐 **소셜 로그인** | 카카오 로그인을 통한 사용자 인증 |
| 🏠 **약속방 생성** | 새로운 약속방 생성 및 초대 |
| 👥 **참여자 관리** | 초대 링크를 통한 약속 참여 및 상태 확인 |
| 📅 **일정 조율** | 참여자들의 약속 일정 조율 |
| 🗺️ **중간 지점 탐색** | 출발지를 기반으로 만날 장소 탐색 |
| 📍 **장소 후보 등록** | 원하는 장소를 후보로 등록 |
| 🗳️ **장소 투표** | 등록된 후보를 바탕으로 투표 진행 |
| 🎉 **최종 장소 확정** | 투표 결과 확인 및 약속 정보 관리 |

<br>

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| **Frontend** | React, TypeScript |
| **Build Tool** | Vite |
| **Styling** | SCSS |
| **Package Manager** | npm |
| **Code Quality** | ESLint, Prettier |
| **Collaboration** | Git, GitHub |

<br>

## 📁 Project Structure

```text
Meetdle_FE/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── feature.md
│   └── PULL_REQUEST_TEMPLATE.md
│
├── public/
│
├── src/
│   ├── assets/         # 이미지 및 정적 리소스
│   ├── components/     # 공통 UI 컴포넌트
│   ├── features/       # 기능별 로직
│   ├── pages/          # 페이지 컴포넌트
│   ├── router/         # 라우팅 설정
│   ├── styles/         # 전역 스타일
│   ├── App.tsx
│   └── main.tsx
│
├── CONVENTION.md
├── eslint.config.js
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

<br>

## 🚀 Getting Started

**1. Repository Clone**

```bash
git clone https://github.com/LIKELION-4THON-TEAM20/Meetdle_FE.git
cd Meetdle_FE
```

**2. Install Dependencies**

```bash
npm install
```

**3. Environment Variables**

`.env.example`을 참고하여 프로젝트 루트에 `.env.local` 파일을 생성하고 환경변수를 설정합니다.

```env
VITE_API_BASE_URL=your_api_base_url
```

> 환경변수 수정 후 개발 서버를 재시작해야 합니다. `.env.local`은 Git에 커밋하지 않습니다.

**4. Run Development Server**

```bash
npm run dev
```

**5. Build & Lint**

```bash
npm run build
npm run lint
```

<br>

## 🔗 Routing & API Integration

Meetdle은 실제 백엔드 API를 기반으로 약속방의 상태와 사용자 역할에 따른 화면을 제공합니다.

| Route | Description |
|---|---|
| `/` | 로그인한 사용자의 약속 목록 |
| `/login` | 카카오 소셜 로그인 |
| `/rooms/create` | 새로운 약속방 생성 |
| `/rooms/:roomId` | 약속방 상태 및 진행 단계 확인 |
| `/invite/:token` | 초대 링크를 통한 참여 |
| `/invitations/:token` | 초대 정보 확인 |
| `/rooms/invite` | 초대 코드 확인 및 참여 |

<details>
<summary><b>📌 상세 약속 진행 경로 보기</b></summary>

<br>

- `/rooms/create/complete`
- `/rooms/schedule-transit`
- `/rooms/participation-status`
- `/rooms/candidates`
- `/rooms/confirmed`
- `/rooms/info`
- `/rooms/registration/setup`
- `/rooms/places`
- `/rooms/registration/status`
- `/rooms/registration/close`
- `/rooms/vote/start`
- `/rooms/vote`
- `/rooms/vote/status`
- `/rooms/vote/result`

해당 경로들은 실제 약속방의 UUID를 `roomId` 쿼리로 전달받아 동작합니다. 유효하지 않은 ID에는 방 선택 안내를 표시합니다.

</details>

### API Integration Principles

- 실제 로그인 세션과 백엔드 API 응답을 기준으로 화면을 구성합니다.
- 약속방 진행 단계와 사용자 역할은 서버 응답을 따릅니다.
- API 요청 실패 시 임의의 예시 데이터로 대체하지 않습니다.
- 데이터가 없는 경우 적절한 빈 상태 화면을 표시합니다.
- 지도 중심, 반경, 장소 후보 및 확정 상태는 서버 데이터를 사용합니다.
- 테스트용 fixture는 애플리케이션의 실제 데이터 흐름과 분리합니다.

<details>
<summary><b>⚙️ 개발 및 배포 시 참고 사항</b></summary>

<br>

- 테스트 데이터는 `tests/fixtures`에서 관리합니다.
- 이전 목 데이터 기반 화면 및 임시 방 저장소는 제거했습니다.
- `/dev/preview`, `?preview=mock` 및 과거 목 방 ID를 통한 화면 확인은 지원하지 않습니다.
- 기존 SCREEN 문서의 목 화면 설명은 현재 동작과 다를 수 있습니다.
- 배포 환경에서 하위 경로 직접 접속 및 새로고침을 지원하려면 SPA fallback 설정이 필요합니다.
- 실제 인증 세션의 서버 쓰기와 종단 간 QA는 별도 검증이 필요합니다.

</details>

<br>

## 🌿 Git Branch Strategy

```text
main
 └── develop
      └── test/integration-flow
           ├── feat/*
           ├── fix/*
           └── refactor/*
```

| Branch | Description |
|---|---|
| `main` | 최종 배포 브랜치 |
| `develop` | 프론트엔드 통합 개발 브랜치 |
| `feat/*` | 신규 기능 개발 |
| `fix/*` | 버그 수정 |
| `refactor/*` | 코드 구조 개선 |
| `test/integration-flow` | 기능 통합 및 전체 흐름 검증 |

**Integration Workflow**

`Feature Development` → `Pull Request` → `Integration Testing` → `Team Review` → `develop`

기능별 PR을 통합 브랜치에 병합하여 전체 흐름을 검증한 후, 팀 리뷰를 거쳐 `develop`에 반영합니다.

<br>

## 📝 Commit Convention

| Type | Description |
|---|---|
| `FEAT` | 기능 및 화면 추가 |
| `FIX` | 버그 수정 |
| `STYLE` | CSS 및 UI 수정 |
| `CHORE` | 설정 및 기타 작업 |
| `REFACTOR` | 코드 구조 개선 |

**Example**

```text
FEAT: 홈 화면 구현
FIX: 장소 등록 상태 처리 수정
CHORE: 프론트엔드 초기 세팅
```

<br>

## 🤝 Collaboration Rules

팀원 간 일관된 개발 환경과 코드 품질을 유지하기 위해 다음 원칙을 적용합니다.

- `main`, `develop` 브랜치 직접 push 금지
- 최신 `develop`을 기준으로 작업 브랜치 생성
- Issue 및 Pull Request 기반 협업
- 코드 리뷰 후 병합
- 통합 작업 시 PR 대상 브랜치 확인
- 공통 컴포넌트 수정 시 팀원에게 공유
- ESLint 및 Prettier를 통한 코드 스타일 통일

자세한 협업 규칙은 [CONVENTION.md](CONVENTION.md)를 참고하세요.

---

<div align="center">

### 📍 Meetdle

**Better Place, Better Meet.**

Made with 💜 by **LIKELION 4호선톤 TEAM 20**

</div>
