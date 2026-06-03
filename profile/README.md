# 학습자료 연계형 통합 퀴즈 운영 시스템 구축 (Edu-Quiz Hub)
## 산학협력 Capstone Project
<br>
<img width="1180" height="366" alt="eduhub_logo" src="https://github.com/user-attachments/assets/fcc9b187-1596-47d0-b11b-e25d3642229e" /><br>

## 🌟프로젝트 소개🌟<br>
### 본 프로젝트는 학습자료 업로드부터 퀴즈 제작, 다목적 설문 운영 및 관리까지 한 곳에서 처리할 수 있는 통합 시스템인 'EDU-HUB' 구축을 목표로 한다.
<br><br><br>
## 🌟기획 배경🌟<br>
현재 교육 현장에서는 강사가 수업에 활용하는 교수 자료(PDF, PPT 등)와 이에 대응하는 퀴즈·평가 도구가 **서로 다른 플랫폼에 분산되어 파편화된 형태로 관리**되고 있다.<br>
강사는 수업 자료를 배포한 뒤 별도의 도구로 문항을 제작하고, 자료와 문제를 일일이 대조하며 구성해야 하므로 불필요한 반복 작업이 발생하고 업무 부담이 가중되는 문제가 있다.<br><br>

학생 입장에서도 어려움은 마찬가지다. 수업 자료는 LMS로 받고, 퀴즈는 별도의 설문 도구로 응시하며, 오답이 발생해도 관련 학습 자료로 즉시 **연결되지 않아** 자기주도적 보완 학습이 어렵다.<br>
학습 콘텐츠가 단절된 상태로 운영되다 보니 학생의 학습 몰입도와 복습 효율이 저하되는 구조적 한계가 존재한다.<br><br>

이러한 문제를 해결하고자, **교수 자료 관리·퀴즈 출제·수강 관리를 하나의 플랫폼에서 처리할 수 있는 통합 교육 관리 시스템(EDU-HUB)** 을 개발하게 되었다.<br>
EDU-HUB는 강사가 교안 PDF를 업로드하고, 해당 자료와 직접 연결된 퀴즈를 등록하며, 수강생의 학습 현황을 한눈에 관리할 수 있도록 설계되었다. 학생은 수강 승인된 강의의 교안을 열람하고 퀴즈를 풀며, 오답 발생 시 연관 교안으로 즉시 이동해 부족한 부분을 바로 보완할 수 있게 한다.<br><br>
<br><br><br>
## 🌟팀원 소개🌟<br>

### 😆정세영 [@Crispylux](https://github.com/Crispylux) (Leader) - Frontend, Database
- **팀장으로서 Github Organization의 전반적인 관리 및 프로젝트 총괄**<br><br>
- **React 기반 프론트엔드**
  	- 홈 랜딩 화면 구현
	- 로그인(교수, admin: 아이디, 비밀번호 이용 / 학생: 카카오 로그인) / 회원가입 화면 구현
   	- 학생 강의 수강 신청 화면 구현
   	- pdf 교안 뷰어 화면 구현
   	- admin 관리자 화면 구현: 학생 강의 수강 신청 승인, 교수 회원가입 신청 승인<br><br>
- **Supabase(Postgre) 데이터베이스 구축, DB 클라우드 서버 관리**
<br><br>

**기술 스택**<br>
`React19` `JavaScript` `CSS` `Vite 8` `Axios` `PostgreSQL(Supabase)`<br><br>

### 😆윤정수 [@jungsu97](https://github.com/jungsu97) - Frontend
- **React 기반 프론트엔드**
	- 학생/교수 메인페이지 UI 설계 및 구현
	- 교안 조회 및 PDF 뷰어 화면 구현
  	- 객관식·주관식 퀴즈 응시 화면 구현
    - 퀴즈 결과 및 해설 조회 화면 구현
<br><br>

**기술 스택**<br>
`React19` `JavaScript` `CSS` `Vite 8` <br><br>

### 😆최민식 [@Kyriepy](https://github.com/Kyriepy) - Backend
**담당 기능**
- 프로젝트 초기 도메인 엔티티 및 DB 스키마 설계
- JWT 인증 필터, Refresh Token Rotation 흐름 구현
- Kakao OAuth2 / OIDC 소셜 로그인 — 신규 유저 pending 토큰 흐름 포함
- PROF / USER 회원가입 분리 (로컬 / 카카오 분기)
- PROF 계정 ADMIN 승인 워크플로 (PENDING → ACTIVE / REJECTED)
- 퀴즈 도메인 구현 — PROF 본인 필터, Hibernate 소프트 삭제, 채점
- 학생 수강 신청 및 컨텐츠 접근 게이팅 (APPROVED 강의만 접근)
- 강의 / 교안 도메인 분리 (lesson 1:N lecture_material 계층 구조)
- ArchUnit 도입 — domain 계층의 보안 구현 의존 자동 차단
- 서비스 레이어 단위 테스트 작성 (JUnit5 + Mockito, 30케이스)
- 아키텍처 문서화 및 exec-plan 기반 작업 흐름 수립

**기술 스택**  
`Java 21` `Spring Boot 3` `Spring Security` `JWT (jjwt)` `Kakao OAuth2 / OIDC` `JPA / Hibernate` `@SQLDelete + @SQLRestriction` `ArchUnit` `JUnit5` `Mockito` `Flyway` `PostgreSQL (Supabase)` <br><br>


### 😆김지훈 [@hooons0228](https://github.com/hooons0228) - Backend
**담당 기능**
비밀번호 재설정 기능 구현 (이메일 유효성 검증 → 재설정 메일 발송 → 토큰 검증 → 새 비밀번호 저장 4단계 플로우)
Redis 기반 재설정 토큰 관리 및 1분 쿨다운 로직 구현
퀴즈 도메인 학생 조회 기능 개선 — lessonId 파라미터 지원 추가
교안 상세 조회 API (/api/materials/{materialId}) PDF URL 응답 추가
최종 프로그램 시연 영상 제작

기술 스택 Java 21 Spring Boot 3 Spring Security JWT (jjwt) JPA / Hibernate Redis JavaMailSender Flyway PostgreSQL (Supabase)<br><br><br>

## 🌟기능 소개(영상)🌟<br>
### 🔥핵심 기능
**[교안/퀴즈 관리, 교안 열람, 퀴즈 열람 및 응시 기능]** <br>
강사(교수)는 교안/퀴즈를 업로드하고 생성할 수 있다. <br>
학생과 강사는 교안을 열람할 수 있으며, 학생은 자신에게 접근 권한이 있는 퀴즈를 열람하고 응시할 수 있다. <br><br>
**[접근 권한 관리]** <br>
관리자가 관리자 화면에서, 학생의 교안 및 퀴즈의 접근 권한을 관리할 수 있다.<br><br>

### 🔥적용 기술
● 프로젝트 관리: `Git`, `Notion`, `Figma(wireframe)`, `Gantt chart`<br>
● DB, DB Cloud Server: `Supabase(PostgreSQL)`<br>
● FrontEnd: `React`<br>
● BackEnd: `Java 21`, `Spring Boot 3`, `Spring Security JWT (jjwt)`, `Kakao OAuth2 /OIDC, JPA / Hibernate`, `ArchUnit`, `JUnit5`, `Mockito`, `Flyway`<br><br>

### 🔥제작과정
폭포수 개발 기법에 애자일 개발 방법을 혼합하여 개발을 진행하였다.<br>
github organization의 frontend, backend repository를 나누어, issue를 생성해 개발 진행 상황을 공유하였다. <br>
매주 google meets를 활용한 회의를 통해, 멘토 피드백을 받고, 각자의 개발 진행 상황과 back-front 개발 명세를 맞추었다.<br><br>

### 🔥랜딩 페이지
<img width="800" height="450" alt="Landingpage" src="https://github.com/user-attachments/assets/28a59565-7d38-4916-beab-f38bfe56e84b" />

<br>

### 🔥사용 흐름

### 👉학생(STUDENT) <br>
**회원가입 및 로그인** : 카카오 소셜 로그인으로 인증한다. 가입 이력이 없을 시 카카오 회원가입을 하게 되고, 최초 1회 닉네임을 설정하게 된다.<br>
<img width="800" height="450" alt="stud_signup" src="https://github.com/user-attachments/assets/f1b40000-0bc8-47ee-8ccd-99459d98d15e" />
<br><br>

**강의 수강신청** : 개설된 강의 목록을 조회하고 원하는 강의에 수강 신청한다. 신청은 관리자의 수락 전까지 대기 상태로 유지된다.<br>
<img width="800" height="450" alt="stud_set" src="https://github.com/user-attachments/assets/9aff5bc9-a85f-4678-a0bb-ffcdec038760" />
<br><br>

**교안 PDF 열람** : 수강 승인된 강의에 한해 교수가 업로드한 교안 PDF를 뷰어에서 조회할 수 있다. 미승인 강의의 교안은 접근이 차단된다.<br>
<img width="800" height="450" alt="stud_pdf" src="https://github.com/user-attachments/assets/ac9cd0cf-8bd5-4602-ba24-fda0b11d772b" />
<br><br>

**퀴즈 풀기** : 수강 중인 강의에 연결된 퀴즈를 풀 수 있다. 오답 발생 시 해당 문제와 연결된 교안 참조 자료가 함께 제공되어 즉각적인 보완 학습이 가능하다.<br>
<img width="800" height="450" alt="stud_quiz" src="https://github.com/user-attachments/assets/d38f07cd-23d1-4f0b-9976-72fb30e6c697" />

<br><br><br>

### 👉교수(PROFESSOR) <br>
**회원가입** : 메일 인증을 통해 본인인증 후 회원가입을 할 수 있다. 회원가입 후 관리자의 승인을 받아야 교수 기능이 활성화된다. 승인 전에는 강의 개설 등 교수 전용 기능이 제한된다.<br>
<img width="800" height="450" alt="Signup" src="https://github.com/user-attachments/assets/99b7aef6-3a03-4e68-a048-fa15b2ad2cc2" />
<br><br>

**강의 개설** : 강의명, 설명 등 정보를 입력해 강의를 개설한다. 개설된 강의는 학생 수강 신청 대상 목록에 노출된다.<br>
**교안 PDF 업로드** : 강의별로 교안 PDF 파일을 업로드한다. 본인이 개설한 강의에만 업로드 권한이 부여되며, 파일 형식 및 용량 제한이 적용된다.<br>
<img width="800" height="450" alt="prof_pdf" src="https://github.com/user-attachments/assets/dc0adbc3-b869-4310-9ec9-988509395bab" />
<br><br>

**퀴즈 등록** : 강의에 퀴즈를 등록하고 특정 교안과 연결한다. 오답 시 참조할 교안을 지정함으로써 문제-근거 자료를 유기적으로 연결한다.<br>
<img width="800" height="450" alt="prof_quiz" src="https://github.com/user-attachments/assets/8dea1ada-d97f-4bca-b1c0-d2731be30b7f" />

<br><br><br>

### 👉관리자(ADMIN) <br>
**교수 가입 승인** : 교수 권한으로 가입한 사용자를 확인하고 승인 또는 거절한다. 승인 전까지 해당 계정은 교수 기능이 비활성화 상태로 유지된다.<br>
<img width="800" height="450" alt="P-1" src="https://github.com/user-attachments/assets/cc300b2e-022b-4842-aec2-5068a79b1a8d" />
<br><br>

**수강 신청 현황 확인 + 수락** : 전체 강의의 수강 신청 현황을 조회하고 관리한다. 비정상적인 신청 또는 계정 이상 여부를 모니터링한다.
<img width="800" height="450" alt="admin_2" src="https://github.com/user-attachments/assets/2fdea747-6931-4d6d-9614-1b0f4c9e4051" />


<br><br><br>

## 🌟로드맵🌟<br>
<img width="1274" height="715" alt="cicd" src="https://github.com/user-attachments/assets/2b2c7f44-238d-45dd-abdf-172cf4d8bfa2" />


<br><br><br>
## 🌟간트 차트🌟<br>
<img width="3307" height="2339" alt="EDU_HUB_WBS_간트차트_제출용_통일색상-1" src="https://github.com/user-attachments/assets/ad9ee963-9b65-48b3-a71f-88214b5b2f38" />

<br><br>

## 🌟와이어프레임🌟<br>
<img width="24039" height="16167" alt="P22CapstoneDesign" src="https://github.com/user-attachments/assets/dc762f58-8d0b-4058-8da7-57e42d755916" />

<br><br><br>

## 🌟ERD🌟<br>
<img width="3116" height="1749" alt="CapstoneERD" src="https://github.com/user-attachments/assets/3029669f-a558-428c-859e-54d954fe9a5f" />

<br><br><br>

<br><br><br>
## 🌟트러블슈팅🌟<br>
**과제 수행과정에서의 문제점 및 시행착오**<br>
프론트·백엔드 간 API 문서 갱신이 지연되어, 실제 구현과 명세가 어긋나는 연동 오류가 반복적으로 발생했다. 대표적인 사례로, 교안-강의자료 분리 작업 중 lesson_material.lesson_id 컬럼이 DB에 반영되지 않아 교안 생성 API가 500 오류를 반환하는 문제와,  Supabase 연결 풀 포화로 서버 기동 자체가 실패하는 환경 이슈가 발생했다.
<br><br>
**문제점 해결과정**<br>
와이어프레임을 기준으로 백엔드 API 명세를 먼저 확정한 뒤, GitHub docs/ 폴더에 즉시 push하여 프론트·백엔드가 동일한 문서를 참조하는 협업 체계를 구축했다. DB 스키마 변경은 마이그레이션 SQL 파일로 표준화해 버전 이력을 명확히 관리했으며, ArchUnit 아키텍처 테스트를 도입해 계층 간 의존 규칙 위반을 빌드 단계에서 자동으로 검출하도록 했다. 기능 구현 후에는 화면 단위 수동 테스트 시나리오를 exec-plan 문서에 명시하고 주기적으로 검증했다.
<br><br>
**추후 개선방향**<br>
실제 배포 후 교수자·학생의 피드백을 수렴하여 UI 및 편의 기능을 지속적으로 개선한다. 강의 시작·종료 시점에 사전·사후 설문 조사 기능을 추가하여 학습 효과를 정량적으로 측정할 수 있는 기반을 마련한다. 현재 부재한 서비스 레이어 단위 테스트를 보완해 안정적인 CI/CD 환경을 구축하고, 오답 발생 시 관련 교안을 자동 연결하는 기능을 개인화 학습 경로 추천으로 발전시킬 계획이다.
<br><br><br>

## 🌟기대효과🌟<br>
본 시스템의 도입을 통해 교수자와 학습자 모두에게 실질적인 이점을 제공할 수 있다.<br><br>

첫째, 지식 자산의 체계화 측면에서, 교안·강의자료·문제 은행을 단일 플랫폼에 통합 저장함으로써 기존에 분산되어 관리되던 교육 콘텐츠를 구조화된 형태로 축적할 수 있다. 이를 통해 반복적인 자료 탐색 시간을 절감하고, 우수 콘텐츠의 재사용성을 높일 수 있다.<br>

둘째, 자료와 연계된 퀴즈 통합 관리를 통해 교수자의 업무 부담을 경감한다. 문제 출제·배포·채점 과정을 자동화하고, 학습 현황 데이터를 대시보드로 제공함으로써 교수자가 수업 설계와 피드백에 집중할 수 있는 환경을 구성한다.<br>

셋째, 문제-근거 자료의 유기적 연결을 통해 즉각적인 보완 학습 환경을 제공한다. 학생이 문제를 틀렸을 때 관련 교안의 해당 항목으로 바로 연결하여 자기주도적 복습이 가능하도록 하며, 반복 오답 패턴 분석을 통해 맞춤형 학습 경로 추천에도 활용할 수 있다.
<br><br><br>

## 🌟회고🌟<br>
### 정세영
**Keep — 잘된 것**
- 현재 학습 플랫폼들을 충분히 조사하고, 교안과 퀴즈가 연결되어 함께 관리되고 학습되기 어렵다는 점을 보완한 플랫폼을 만들자는 프로젝트의 목표를 벗어나지 않고 달성했다
- 사용자 편의를 고려한 UI/UX를 제공하려 테스트 사용자들의 피드백을 받아 주기적으로 수정을 거쳤다
- Github의 commit 기록을 바탕으로, 매주 회의를 열어 현재 진행 상황 공유 및 상호 피드백과 코드리뷰를 통해 오류가 생기는 부분을 원활하게 소통하여 일정의 차질을 줄였다

**Problem — 아쉬운 것**
- 와이어프레임이 빠르게 확정되지 않아 API 명세에 혼동이 발생하였고, 백엔드와 프론트엔드의 명세가 어긋나는 문제로, 개발이 지연되었다
- 초기 상단바 세팅을 공통 프로그램을 공유하지 않아 반복적인 중복 코딩의 문제가 생겼다
- DB 컬럼명의 혼동으로, Nickname과 username이 함께 쓰여 백엔드와 프론트엔드 매핑의 문제가 있었다
- 화면 단위 (서비스 레이어) 테스트를 개발 이후 한 번에 해서, 디버깅에 시간이 많이 소요되었다. 레이어 단위 테스트를 빠르게 진행했다면 테스트 후 디버깅 시간이 줄었을 것이다

**Try — 다음에 시도할 것**
- 학생 수강 신청 화면에서, 현재 자신이 수강하는 과목의 목록을 조회할 수 있는 UI가 있도록 한다
- 휴대폰 본인 인증 시스템을 추가하여, 회원가입의 메일 인증을 대체하거나, 아이디 찾기를 추가할 수 있도록 한다
- 관리자의 강의 수강 신청 승인이나 교수 회원가입 대기 승인 시, 승인이 완료되었다는 메일이 갈 수 있도록 한다
- 모바일 화면 비율에 맞춰 작동될 수 있게 한다
<br><br>
### 윤정수

**Keep — 잘된 것**
- 퀴즈 화면을 기간 내에 잘 완료 하였다
- 팀원들과 소통하며 오류를 수정하고 개선하였다
- Figma를 활용하여 화면 설계를 진행했다<br><br>
**Problem — 아쉬운 것**
- 프론트엔드 개발 경험이 부족해 구현에 시간이 오래 걸렸다
- 초기 화면 설계에 미흡한 부분이 많아 프로젝트 중후반 화면 설계가 여러 번 변경되었다
- 코드 구조를 늦게 이해하여 고치지 못한 부분이 있었다<br><br>
**Try — 다음에 시도할 것**
- React와 프론트엔드 기술을 더 학습하기
- 컴포넌트 구조를 미리 설계하고 개발하기
- 초기 기획 단계에서 화면 설계를 더 구체적으로 진행하기
<br><br>
### 최민식

**Keep — 잘된 것**
- `CLAUDE.md`와 `docs/exec-plans/`를 통한 문서 주도 개발: 설계 → 승인 → 구현 흐름을 지켜 기능 중간에 방향이 흔들리는 일이 거의 없었다
- ArchUnit으로 아키텍처 규칙을 테스트로 강제한 것: domain 서비스가 JWT · Security 구현체에 의존하는 실수를 빌드 단계에서 자동 차단해 코드 리뷰 부담이 줄었다
- `isOwner(Long id, Long userId)` 형태로 소유자 검증 통일: 서비스 계층이 Spring Security 객체에 의존하지 않아 단위 테스트 작성이 쉬웠다
- `troubleshooting/` 문서화: 같은 원인의 버그(`ddl-auto`와 NOT NULL 컬럼 추가 불가)가 반복될 뻔했으나 기록 덕분에 즉시 원인을 특정할 수 있었다

**Problem — 아쉬운 것**
- 초기 아키텍처에서 domain 서비스가 `CustomUserDetails`를 직접 받는 구조로 작성돼 ArchUnit 도입 시 전면 리팩터링이 필요했다. 처음부터 보안 객체를 서비스에 넘기지 않는 규칙을 세웠더라면 줄일 수 있었던 작업이었다
- `ddl-auto: update` 의존으로 DB 마이그레이션 문제가 반복됐다: 강의/교안 분리 후 `lecture_material.lesson_id` 미추가, `quiz.lesson_id` 잔존 등 세 건의 트러블슈팅 이슈가 연달아 발생했다. Flyway를 처음부터 썼으면 막을 수 있었다
- 서비스 레이어 단위 테스트를 기능 개발 이후 별도 브랜치로 몰아 작성했다. 기능과 테스트를 같이 짰다면 버그를 더 일찍 잡을 수 있었을 것이다
- `@PreAuthorize` 거부 시 500이 반환되는 예외 처리 누락이 초기에 잡히지 않고 프론트 연동 단계에서 발견됐다

**Try — 다음에 시도할 것**
- Flyway를 프로젝트 시작 시점에 도입해 스키마 변경을 SQL 파일로 관리한다. `ddl-auto: update`는 로컬 실험 전용으로만 사용한다
- 아키텍처 규칙(ArchUnit)과 서비스 인터페이스 설계를 첫 커밋에 포함해 팀원 모두가 같은 기준에서 시작하도록 한다
- 기능 단위 PR에 서비스 테스트를 함께 포함하는 정책을 enforce한다
- TestContainers로 Redis · PostgreSQL을 격리해 `@SpringBootTest` 풀 통합 테스트를 CI에서 실행한다
<br><br>
### 김지훈

**Keep — 잘된 것**

비밀번호 재설정 기능을 이메일 유효성 검증 → 메일 발송 → 토큰 검증 → 새 비밀번호 저장의 4단계 플로우로 체계적으로 설계하고, JWT 인증 없이 접근 가능한 퍼블릭 API로 구현하였다
권한 처리 로직을 사용자 역할(Role) 확인 → 자료 소유자 여부 확인의 단계적 검증 구조로 설계하여, 교수/학생/관리자 각각의 접근 범위를 명확하게 분리하였다
트러블슈팅 과정에서 로그를 적극적으로 활용하여 문제 원인을 빠르게 파악하는 습관을 가졌다

**Problem — 아쉬운 것**

프론트엔드와 API 파라미터 명세를 사전에 충분히 협의하지 않아 lessonId와 materialId 혼동으로 인한 연동 오류가 발생하였고, 디버깅에 많은 시간이 소요되었다
브랜치 병합 시 application.yml의 OAuth2 설정이 소실되는 문제가 발생하였는데, 팀원과 사전에 설정 파일 관리 방식을 합의했더라면 방지할 수 있었다
Flyway 마이그레이션 버전 번호를 팀원과 사전에 협의하지 않아 브랜치 병합 후 V3/V4 순서 충돌이 발생하였다
권한 오류 발생 시 원인을 바로 찾지 못해 디버깅에 시간이 많이 소요되었다. 레이어 단위 테스트를 빠르게 진행했더라면 디버깅 시간이 줄었을 것이다

**Try — 다음에 시도할 것**

프론트엔드와 API 명세를 개발 시작 전 문서로 먼저 확정하고, 파라미터 이름과 타입을 명확히 합의한 뒤 개발을 시작한다
application.yml을 Git 추적에서 제외하고 .env 또는 별도 템플릿 파일로 팀원 간 설정을 공유하는 방식을 도입한다
Flyway 마이그레이션 파일의 버전 번호를 팀원과 사전에 배분하여 충돌을 방지한다
기능 개발과 함께 서비스 레이어 단위 테스트를 작성하여 버그를 조기에 발견할 수 있도록 한다
