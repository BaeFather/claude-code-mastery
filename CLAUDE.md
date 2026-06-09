# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

개발자 이력서 및 포트폴리오를 소개하는 **반응형 웹 포트폴리오 사이트**입니다. HTML5, CSS3, TailwindCSS, Vanilla JavaScript로 구현되는 정적 웹사이트입니다.

**참고**: 상세한 개발 로드맵은 `ROADMAP.md`를 참조하세요.

---

## 언어 및 커뮤니케이션 규칙

이 프로젝트에서 Claude Code가 따를 언어 규칙:

- **기본 응답 언어**: 한국어
- **코드 주석**: 한국어로 작성
- **커밋 메시지**: 한국어로 작성
- **문서화 (README, CLAUDE.md 등)**: 한국어로 작성
- **변수명/함수명**: 영어 (코딩 표준 준수)
- **클래스명/ID명**: 영어 (웹 표준 준수)

---

## 기술 스택

| 분류 | 기술 |
|------|------|
| **마크업** | HTML5 (시맨틱 태그) |
| **스타일링** | CSS3 + TailwindCSS |
| **인터랙션** | Vanilla JavaScript (ES6+) |
| **패키지 관리** | npm |
| **배포** | GitHub Pages / Vercel / Netlify (미결정) |

---

## 프로젝트 구조

```
claude-code-mastery/
├── index.html              # 메인 HTML 파일 (단일 페이지)
├── css/
│   └── style.css          # 커스텀 CSS (TailwindCSS 기본값 오버라이드)
├── js/
│   ├── main.js            # 메인 JavaScript 파일
│   ├── smooth-scroll.js   # 부드러운 스크롤 기능
│   ├── mobile-nav.js      # 모바일 네비게이션 기능
│   └── animations.js      # 스크롤 애니메이션 (Intersection Observer)
├── assets/
│   ├── images/            # 프로필 사진, 프로젝트 이미지
│   └── fonts/             # 커스텀 폰트 (필요시)
├── tailwind.config.js     # TailwindCSS 설정
├── postcss.config.js      # PostCSS 설정
├── package.json           # npm 프로젝트 설정
├── .gitignore             # Git 무시 파일
├── ROADMAP.md             # 개발 로드맵 및 마일스톤
└── CLAUDE.md              # 이 파일
```

---

## 일반적인 명령어

### 초기 셋업
```bash
npm install                 # 의존성 설치
```

### 개발
```bash
npm run dev                 # TailwindCSS 감시 모드 + 개발 서버
                            # (라이브 리로드 포함)
```

### 프로덕션 빌드
```bash
npm run build               # CSS 퍼징을 통한 프로덕션 최적화
```

### 기타
```bash
npm run lint                # 코드 스타일 검사 (추후 설정)
npm run preview             # 프로덕션 빌드 결과 미리보기
```

---

## 개발 워크플로우

### 1. 기능 개발 순서

프로젝트는 다음 순서로 개발합니다:

1. **Phase 0 - 프로젝트 셋업**: npm, TailwindCSS 초기화
2. **Phase 1 - HTML 구조**: 시맨틱 마크업으로 섹션 구성
3. **Phase 2 - 스타일링**: TailwindCSS로 반응형 디자인
4. **Phase 3 - 인터랙션**: JavaScript로 기능 구현
5. **Phase 4 - 콘텐츠**: 실제 데이터 입력
6. **Phase 5 - 최적화**: 성능, 접근성, 브라우저 호환성 검증
7. **Phase 6 - 배포**: GitHub Pages/Vercel/Netlify 선택하여 배포

### 2. 주요 섹션 구성

포트폴리오 사이트는 다음 섹션으로 구성됩니다:

- **Navigation Bar**: 로고, 메뉴 링크 (스티키 또는 고정)
- **Hero Section**: 자기소개, 프로필 사진, CTA 버튼
- **About Section**: 경력, 교육, 주요 성취
- **Skills Section**: 기술 스택 (분류: Languages, Frontend, Backend, Tools)
- **Experience Section**: 직무 경력 정보
- **Projects Section**: 포트폴리오 프로젝트 (카드 레이아웃)
- **Contact Section**: 연락처, 소셜 미디어, 이메일 폼
- **Footer**: 저작권, 추가 링크

### 3. CSS/TailwindCSS 작성 규칙

- TailwindCSS 유틸리티 클래스를 우선 사용
- 반응형 접두사 사용: `sm:`, `md:`, `lg:`, `xl:`, `2xl:`
- 다크모드 지원: `dark:` 접두사 사용
- 필요시에만 `@apply`로 커스텀 컴포넌트 클래스 정의
- 커스텀 CSS는 `css/style.css`에 작성

### 4. JavaScript 작성 규칙

- **Vanilla JavaScript 사용**: 외부 라이브러리 최소화
- **모듈화**: 기능별로 파일 분리 (smooth-scroll.js, mobile-nav.js 등)
- **성능**: Intersection Observer 사용으로 스크롤 애니메이션 최적화
- **이벤트 위임**: 효율적인 이벤트 핸들링
- **캐싱**: 자주 사용되는 DOM 요소는 변수에 캐시

### 5. 반응형 디자인 브레이크포인트

```
Mobile:  < 640px  (sm)
Tablet:  640px - 1024px  (md, lg)
Desktop: > 1024px  (xl, 2xl)
```

---

## 성능 및 최적화

### 이미지 최적화
- WebP 형식 사용 (대체 이미지로 PNG/JPG 제공)
- `srcset`과 `sizes` 속성으로 해상도별 최적화
- Lazy loading 적용 (`loading="lazy"`)

### CSS 최적화
- TailwindCSS의 PurgeCSS로 사용되지 않는 스타일 제거
- 빌드 시 자동으로 최소화

### JavaScript 최적화
- 필요한 스크립트만 로드
- DOM 조작 최소화
- 성능 측정: Lighthouse 점수 80점 이상 목표

---

## 배포

### 배포 옵션 (미결정)

1. **GitHub Pages**: 무료, Git 연동 자동화
2. **Vercel**: 자동 빌드, 뛰어난 성능, 분석 기능
3. **Netlify**: 자동 빌드, 폼 제출 지원, DNS 관리

### SEO 고려사항

- Meta 태그 (description, keywords, og:*)
- Structured Data (Schema.org 마크업)
- 사이트맵 생성
- Mobile-friendly 검증

---

## 코드 리뷰 체크리스트

새로운 기능을 구현할 때 다음을 확인:

- [ ] HTML이 시맨틱하게 구성되었는가?
- [ ] TailwindCSS 클래스를 올바르게 사용했는가?
- [ ] 반응형 디자인이 모든 브레이크포인트에서 작동하는가?
- [ ] JavaScript는 모듈화되어 있는가?
- [ ] 접근성 (aria-label, alt text) 을 고려했는가?
- [ ] 브라우저 호환성을 확인했는가? (Chrome, Firefox, Safari, Edge)
- [ ] 커밋 메시지는 한국어로 의도를 명확히 설명하는가?

---

## 참고 자료

- **ROADMAP.md**: 개발 로드맵 및 마일스톤
- **TailwindCSS 문서**: https://tailwindcss.com
- **MDN Web Docs**: https://developer.mozilla.org
- **Intersection Observer API**: https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API

---

**마지막 업데이트**: 2026년 6월 9일
