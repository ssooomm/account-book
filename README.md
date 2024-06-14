## 슬기로운 가계부 생활


# 가계부 사용자 매뉴얼

## 목차
1. [소개 및 개요](#소개-및-개요)
    - [제품 소개](#제품-소개)
2. [설치 및 설정](#설치-및-설정)
    - [설치 방법](#설치-방법)
    - [요구 사항](#요구-사항)
3. [기능 별 사용법](#기능-별-사용법)
    - [수입 및 지출 추가하기(메인 화면에서)](#1-1-수입-및-지출-추가하기메인-화면에서)
    - [수입 및 지출 추가하기(내역 조회에서)](#1-2-수입-및-지출-추가하기내역-조회에서)
    - [수입 및 지출 조회하기](#2-수입-및-지출-조회하기)
    - [수입 및 지출 수정하기](#3-수입-및-지출-수정하기)
    - [수입 및 지출 삭제하기](#4-수입-및-지출-삭제하기)
    - [가계부 요약 카드 기능](#5-가계부-요약-카드-기능)
    - [소비 지출 보고서](#6-소비-지출-보고서)
4. [문제 해결](#문제-해결)
    - [자주 발생하는 문제 해결](#자주-발생하는-문제-해결)
5. [FAQ](#faq)
    - [자주 묻는 질문](#자주-묻는-질문)
6. [참고 자료](#참고-자료)
    - [추가 리소스](#추가-리소스)
7. [기여 방법](#기여-방법)
8. [라이센스](#라이센스)
9. [스크린샷](#스크린샷)

## 소개 및 개요

### 제품 소개

가계부 소프트웨어는 개인의 수입과 지출을 효과적으로 관리할 수 있도록 돕는 도구입니다. 
이 소프트웨어는 사용자가 지출과 소비를 추가할 수 있고 각 속성 별 정렬이 가능합니다. 
또한 소비와 지출에 대한 차트를 통해 한 번에 볼 수 있게 만들었습니다. 
부트스트랩 탬플릿을 통해 스타일을 적용했고, 반응형 페이지로 구현하여 여러 환경에서 볼 수 있게 구성하였습니다.

## 설치 및 설정

### 설치 방법

1. 레포지토리에서 가계부 소프트웨어를 다운로드합니다.
2. 필요 패키지를 설치합니다.
3. json 서버 3000포트로 실행 후 npm run dev 명령어로 실행합니다.

### 요구 사항

- Node.js (버전 X.X.X 이상)
- npm (버전 X.X.X 이상)

## 기능 별 사용법

### 1-1. 수입 및 지출 추가하기(메인 화면에서)

1. 메인 화면에 `빠른 등록` 찾기
2. 날짜, 분류(입출금), 금액, 카테고리(추가 선택 시 입력가능), 내용을 입력
3. `등록하기` 버튼 클릭

### 1-2. 수입 및 지출 추가하기(내역 조회에서)

1. 메인화면에서 `최근 내역`을 클릭 혹은 상단 메뉴에 `내역` 을 클릭
2. `내역조회` 에 테이블 상단에 위치한 입력폼 확인
3. 날짜, 분류(입출금), 금액, 카테고리(추가 선택 시 입력가능), 내용을 입력
4. `내역추가` 버튼 클릭

### 2. 수입 및 지출 조회하기

1. 메인화면에 `최근 내역`에서 최근 5개의 내역을 조회 가능
2. 메인화면에서 `최근 내역`을 클릭 혹은 상단 메뉴에 `내역` 을 클릭
3. 테이블의 헤더를 클릭 → 해당 속성으로 오름차순 내림차순 정렬 기능
4. 모두 보기 드롭박스로 카테고리 별 내역 조회 가능
5. 한 번에 10개의 내역을 볼 수 있고 `이전` `다음` 버튼으로 페이지를 넘겨가며 조회

### 3. 수입 및 지출 수정하기

1. 메인화면에서 `최근 내역`을 클릭 혹은 상단 메뉴에 `내역` 을 클릭
2. 수정하고 싶은 내역을 테이블에서 클릭
3. 모달 창에서 날짜, 분류(입출금), 금액, 카테고리(추가 선택 시 입력가능), 내용을 입력
4. `변경 저장` 버튼 클릭

### 4. 수입 및 지출 삭제하기

1. 메인화면에서 `최근 내역`을 클릭 혹은 상단 메뉴에 `내역` 을 클릭
2. 삭제하고 싶은 내역을 테이블에서 클릭
3. `삭제`버튼 클릭

### 5. 가계부 요약 카드 기능

1. 해당 달의 총 소득액
2. 해당 달의 총 지출액
3. 지출 계획 & 목표금액 채우기 
    1. 해당 카드에 마우스 올리면 수정 버튼 보여짐
    2. 수정 버튼 클릭 시 지출 목표 설정 가능
    3. 목표를 기준으로 어느정도 달성 했는지 퍼센트로 확인 가능

### 6. 소비 지출 보고서

1. `월 선택 드롭박스`를 통해 월 선택
2. 소득 분석 & 소비 분석
    1. 어떤 카테고리에 소비를 했는지 확인 가능하다.
3. 주 별 요약
    1. `월 선택` 으로 원 선택
    2. 해당 월 주차 별로 소비와 소득을 바 차트로 확인 가능

## 문제 해결

### 자주 발생하는 문제 해결

#### 문제: 프로그램이 실행되지 않습니다.

- 해결 방법: 필요 패키지를 다 설치 했는지 확인해주세요. 그래도 문제가 해결되지 않으면 고객 지원 팀에 문의하세요.

## FAQ

### 자주 묻는 질문

#### Q: 가계부 소프트웨어는 어떤 운영체제에서 작동하나요?

A: 가계부 소프트웨어는 Windows, macOS, Linux에서 작동합니다.

## 참고 자료

### 추가 리소스

- [레포지토리](https://github.com/isj0228/sulgasaeng)
- 설명 PPT
- 사용 탬플릿: https://startbootstrap.com/theme/sb-admin-2
## 기여 방법

1. 이 레포지토리를 포크합니다.
2. 새로운 브랜치를 만듭니다 (`git checkout -b feature/YourFeature`).
3. 변경 사항을 커밋합니다 (`git commit -am 'Add some feature'`).
4. 브랜치에 푸시합니다 (`git push origin feature/YourFeature`).
5. 풀 리퀘스트를 작성합니다.

## 라이센스

이 프로젝트는 MIT 라이센스에 따라 라이센스가 부여됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 스크린샷

### 메인 화면
![메인 화면](https://path-to-screenshot1)

### 내역 조회 화면
![내역 조회 화면](https://path-to-screenshot2)
