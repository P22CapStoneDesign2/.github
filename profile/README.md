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
・ 현재 교육 현장에서 강사가 사용하는 교수자료(PDF, PPT 등)와 그에 해당
하는 퀴즈 및 평가 도구가 **파편화**되어 관리되고 있다.<br>  
・ 강사들은 수업 자료를 배포한 뒤, **별도의 플랫폼이나 파일**로 문제를 제
작하고 관리해야 하므로 자료를 대조하며 문항을 구성하는 과정에서 큰 번
거로움을 겪고 있다.<br>  
・ 또한 퀴즈는 학습 도구로, 설문은 만족도 조사용으로 각각 다른 서비스
를 통해 분리되어 운영되고 있어 **데이터를 통합하여 관리하는 시스템**이 필
요하다.<br>
<br><br><br>
## 🌟팀원 소개🌟<br>

### 정세영(Leader)- Frontend, Database

- **React 기반 프론트엔드**
  	- 홈 랜딩 화면 구현
	- 로그인 / 회원가입 화면 구현
   	- 교안 수강 신청 화면 구현
   	- pdf 교안 뷰어 화면 구현
   	- admin 관리자 화면 구현: 학생 교안 수강 신청 승인, 교수 회원가입 신청 승인
   	  
- **Supabase(Postgre) 데이터베이스 구축, 서버 관리**

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
(영상)
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

