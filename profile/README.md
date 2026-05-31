# 학습자료 연계형 통합 퀴즈 운영 시스템 구축 (Edu-Quiz Hub)
### 산학협력 Capstone Project<br>
**notion:**<br><br>
**=============작성해야 할 것===============**<br>
서비스 소개<br>
기획 배경<br>
기능 소개(영상/gif)<br>
	- 랜딩 화면<br>
	- 로그인 / 회원가입)<br>
	- 학생 화면<br>
	- 교수 화면<br>
	- admin 화면<br>
기술 스택(개발 환경 간단하게-뭘 사용했는지?)(CI/CD 배포 환경 로드맵만 뽑기)<br>
ERD<br>
회고(회의록-산출물 쪽에 있음)<br>
	- KPT<br>
		K : 이 프로젝트를 통해 배우게 된 것<br>
		P : 아쉬운 점<br>
		T : 트러블슈팅에서 미해결된 것들 또는 Develop한다면 시도하고 싶은 것들<br><br>
**====================================**<br><br>
<img width="1180" height="366" alt="eduhub_logo" src="https://github.com/user-attachments/assets/fcc9b187-1596-47d0-b11b-e25d3642229e" /><br>
## 🌟프로젝트 소개🌟<br>
### 본 프로젝트는 학습자료 업로드부터 퀴즈 제작, 다목적 설문 운영 및 관리까지 한 곳에서 처리할 수 있는 통합 시스템인 EDU-HUB 구축을 목표로 한다.
<br><br><br>
## 🌟기획 배경🌟<br>
- 현재 교육 현장에서는 강사가 수업에 활용하는 교수 자료(PDF, PPT 등)와 이에 대응하는 퀴즈·평가 도구가 **서로 다른 플랫폼에 분산되어 파편화된 형태로 관리**되고 있다. 강사는 수업 자료를 배포한 뒤 별도의 도구로 문항을 제작하고, 자료와 문제를 일일이 대조하며 구성해야 하므로 불필요한 반복 작업이 발생하고 업무 부담이 가중되는 문제가 있다.<br><br>

학생 입장에서도 어려움은 마찬가지다. 수업 자료는 LMS로 받고, 퀴즈는 별도의 설문 도구로 응시하며, 오답이 발생해도 관련 학습 자료로 즉시 **연결되지 않아** 자기주도적 보완 학습이 어렵다. 학습 콘텐츠가 단절된 상태로 운영되다 보니 학생의 학습 몰입도와 복습 효율이 저하되는 구조적 한계가 존재한다.<br><br>

이러한 문제를 해결하고자, **교수 자료 관리·퀴즈 출제·수강 관리를 하나의 플랫폼에서 처리할 수 있는 통합 교육 관리 시스템(EDU-HUB)** 을 개발하게 되었다. EDU-HUB는 강사가 교안 PDF를 업로드하고, 해당 자료와 직접 연결된 퀴즈를 등록하며, 수강생의 학습 현황을 한눈에 관리할 수 있도록 설계되었다. 학생은 수강 승인된 강의의 교안을 열람하고 퀴즈를 풀며, 오답 발생 시 연관 교안으로 즉시 이동해 부족한 부분을 바로 보완할 수 있게 한다.<br><br>
<br><br><br>
## 🌟팀원 소개🌟<br>

### 정세영(Leader)- Frontend, Database

- **React 기반 프론트엔드**
  	- 홈 랜딩 화면 구현
	- 로그인(교수, admin: 아이디, 비밀번호 이용 / 학생: 카카오 로그인) / 회원가입 화면 구현
   	- 학생 강의 수강 신청 화면 구현
   	- pdf 교안 뷰어 화면 구현
   	- admin 관리자 화면 구현: 학생 강의 수강 신청 승인, 교수 회원가입 신청 승인<br><br>
- **Supabase(Postgre) 데이터베이스 구축, DB 클라우드 서버 관리**<br><br>
**기술 스택**<br>
`React19` `JavaScript` `CSS` `Vite 8` `Axios` `PostgreSQL(Supabase)`<br><br>
### 윤정수 - Frontend



### 최민식 — Backend

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
`Java 21` `Spring Boot 3` `Spring Security` `JWT (jjwt)` `Kakao OAuth2 / OIDC` `JPA / Hibernate` `@SQLDelete + @SQLRestriction` `ArchUnit` `JUnit5` `Mockito` `Flyway` `PostgreSQL (Supabase)`


### 김지훈 - Backend


<br><br><br>
## 🌟와이어프레임🌟<br>
(사진)
<br><br><br>
## 🌟기능 소개(영상)🌟<br>

#### 🔥핵심 기능
**[교안/퀴즈 관리, 교안 열람, 퀴즈 열람 및 응시 기능]**
강사(교수)는 교안/퀴즈를 업로드하고 생성할 수 있다.
학생과 강사는 교안을 열람할 수 있으며, 학생은 자신에게 접근 권한이 있는 퀴즈를 열람하고 응시할 수 있다.
**[접근 권한 관리]**
관리자가 관리자 화면에서, 학생의 교안 및 퀴즈의 접근 권한을 관리할 수 있다.<br><br>

#### 🔥적용 기술
● 프로젝트 관리: Git, Notion, Figma(wireframe), Gantt chart<br>
● DB, DB Cloud Server: Supabase(PostgreSQL)<br>
● FrontEnd: React<br>
● BackEnd: Java 21, Spring Boot 3, Spring Security JWT (jjwt), Kakao OAuth2 /OIDC, JPA / Hibernate, ArchUnit, JUnit5, Mockito, Flyway<br><br>

#### 🔥제작과정
폭포수 개발 기법에 애자일 개발 방법을 혼합하여 개발을 진행하였다.<br>
github organization의 frontend, backend repository를 나누어, issue를 생성해 개발 진행 상황을 공유하였다. <br>
매주 google meets를 활용한 회의를 통해, 멘토 피드백을 받고, 각자의 개발 진행 상황과 back-front 개발 명세를 맞추었다.<br><br>

#### 🔥사용 흐름
● **학생(STUDENT)** <br>
1. 로그인카카오 소셜 로그인으로 인증한다.<br>
2. 강의 수강신청개설된 강의 목록을 조회하고 원하는 강의에 수강 신청한다. 신청은 관리자의 수락 전까지 대기 상태로 유지된다.<br>
3. 교안 PDF 열람수강 승인된 강의에 한해 교수가 업로드한 교안 PDF를 뷰어에서 조회할 수 있다. 미승인 강의의 교안은 접근이 차단된다.<br>
4. 퀴즈 풀기수강 중인 강의에 연결된 퀴즈를 풀 수 있다. 오답 발생 시 해당 문제와 연결된 교안 참조 자료가 함께 제공되어 즉각적인 보완 학습이 가능하다.<br><br>

● **교수(PROFESSOR)** <br>
1. 로그인 및 교수 승인회원가입 후 관리자의 승인을 받아야 교수 기능이 활성화된다. 승인 전에는 강의 개설 등 교수 전용 기능이 제한된다.<br>
2. 강의 개설강의명, 설명 등 정보를 입력해 강의를 개설한다. 개설된 강의는 학생 수강 신청 대상 목록에 노출된다.<br>
3. 수강 신청 수락강의에 신청한 학생 목록을 확인하고 수락 또는 거절한다. 수락된 학생만 교안 및 퀴즈에 접근할 수 있다.<br>
4. 교안 PDF 업로드강의별로 교안 PDF 파일을 업로드한다. 본인이 개설한 강의에만 업로드 권한이 부여되며, 파일 형식 및 용량 제한이 적용된다.<br>
5. 퀴즈 등록강의에 퀴즈를 등록하고 특정 교안과 연결한다. 오답 시 참조할 교안을 지정함으로써 문제-근거 자료를 유기적으로 연결한다.<br><br>

● **관리자(ADMIN)** <br>
1. 교수 가입 승인교수 권한으로 가입한 사용자를 확인하고 승인 또는 거절한다. 승인 전까지 해당 계정은 교수 기능이 비활성화 상태로 유지된다.<br>
2. 수강 신청 현황 확인 + 수락전체 강의의 수강 신청 현황을 조회하고 관리한다. 비정상적인 신청 또는 계정 이상 여부를 모니터링한다.
<br><br><br>
## 🌟간트 차트🌟<br>
(사진)
<br><br><br>
## 🌟ERD🌟<br>
<img width="3116" height="1749" alt="CapstoneERD" src="https://github.com/user-attachments/assets/3029669f-a558-428c-859e-54d954fe9a5f" />

<br><br><br>
## 🌟배포 로드맵🌟<br>
(로드맵 이미지)
<br><br><br>
## 🌟회고🌟<br>
### 정세영
### 윤정수 
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
- 
### 김지훈

