# 레포지토리 명
## Game-LogData-Pipeline

## 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [프로젝트 기술 스택](#프로젝트-기술-스택)
3. [개발 기간](#개발-기간)
4. [개발 인원](#개발-인원)
5. [스크린샷](#스크린샷)


<br>

### 본 프로젝트는 기업협업 과제로 NDA(비밀유지계약서)를 작성함에 따라 코드를 공개하지 않습니다.

## 프로젝트 개요
- 게임 백엔드 제공 서비스(Backend as a Service) 로그 데이터 데이터 파이프라인 구축
  - 로그 데이터 압축/복원 알고리즘 적용
    - zlip 기반 모듈 gzip 압축 모듈 사용(약 85% 압축)
    - uuid(64bytes)를 b64uuid를 통하여 44bytes로 압축
    - 압축 모듈 + 문자열 압축 알고리즘 적용 : 88.4% 압축
    - 원래 사이즈대로 복원하는 알고리즘 적용
  - AWS Lambda + CloudWatch Trigger를 통한 배치 처리 스케쥴링 구현
  - AWS S3 파티셔닝 저장기능 추가
  - AWS S3 저장, AWS Athena 활용 데이터 조회 기능
  - 대쉬보드 기능 적용


<br>

### 프로젝트 시작 배경
- 백엔드 서비스에서 하루에 200GB이상 발생하는 로그 데이터 보관의 어려움

<br>

### 프로젝트 진행과정
- 데이터 용량 문제를 해결하기 위한 압축 알고리즘 탐색 후 구현 및 적용(gzip 모듈) - 5일 소요
- gzip 모듈에서 제공하는 압축율(약 85%) 개선을 위해 문자열 압축 적용(uuid: 64bytes -> b64uuid: 44bytes) - 7일 소요
- 데이터 파이프라인 구축을 위해 Apache Spark, Apache Kafka, AWS Kinesis, AWS Lambda 사용 후 비교 - AWS Lambda + CloudWatch로 배치 처리 스케쥴링 진행 - 10일 소요
- AWS S3에 파티셔닝 기능 추가하여 저장 - 5일 소요

<br>

### 한계점 및 해결 방안
- 한계점
  - 처음 접하는 툴이 많고, 제한된 시간안에 목표한 기능을 구현하기 위해 많은 시간을 소비함에 따라 시간 분배에 실패함
  - 다양한 툴을 사용함에 있어서 최적화를 고려하지 않고 기능 구현에만 집중함
- 해결 방안
  - 정해진 시간에 목표를 달성하는데 최선을 다하되, 시간이 초과한다면 다음 일정을 소화할 수 있도록 시간 분배에 초점을 두어야함
  - 해결하지 못한 문제는 자투리 시간을 활용하여 시도해보도록 함
  - 기능 구현을 우선으로 하되 현재 상황에 적용할 수 있는 더 많은 가능성에 대한 고려를 해야함

<br>

## 프로젝트 기술 스택

### PipeLine
<section>
<img src="https://img.shields.io/badge/Python-3776AB?logo=Python&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS%20Lambda-FF9900?logo=AWS%20Lambda&logoColor=white"/>
<img src="https://img.shields.io/badge/Amazon%20CloudWatch-FF4F8B?logo=Amazon%20CloudWatch&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS%20S3-569A31?logo=AWS%20S3&logoColor=white"/>
</section>


### Tools
<section>
<img src="https://img.shields.io/badge/GitHub-181717?logo=GitHub&logoColor=white"/>
<img src="https://img.shields.io/badge/Discord-5865F2?logo=Discord&logoColor=white">
</section>




## 개발 인원
| 김현수 | 조용원 | 김영우
| ------ | ------ | ------ |
| 데이터 파이프라인 구축| AWS S3 파티셔닝, AWS Athena 사용 정리, 대쉬보드 구현| 압축 알고리즘 개선|
| [Github](https://github.com/HyeonsooKim) | [Github](https://github.com/joyw93) | [Github](https://github.com/nywkim)


<br>


## 개발 기간
- 2021/12/24~2022/01/19 (27일)


<br>

## 스크린샷
<img width="721" alt="스크린샷 2022-10-04 오전 11 41 14" src="https://user-images.githubusercontent.com/48047773/193722978-b8bdaca2-bcd0-42ad-b019-9cadac69ff76.png">

<img width="940" alt="스크린샷 2022-09-16 오후 5 39 10" src="https://user-images.githubusercontent.com/48047773/193195042-8e50cb11-f1ee-4516-8c5b-7a66989ba4a1.png">

<img width="873" alt="스크린샷 2022-09-16 오후 5 39 44" src="https://user-images.githubusercontent.com/48047773/193195071-35e86c5e-7034-41a1-b06a-4730193f09d6.png">
<img width="925" alt="스크린샷 2022-09-16 오후 5 40 15" src="https://user-images.githubusercontent.com/48047773/193195078-a1dd8e6b-5247-418d-bc7e-b73b0b963c56.png">
<img width="786" alt="스크린샷 2022-09-16 오후 5 40 29" src="https://user-images.githubusercontent.com/48047773/193195095-1f579793-4783-4400-8b4a-2423610c5191.png">
<img width="908" alt="스크린샷 2022-09-16 오후 5 40 41" src="https://user-images.githubusercontent.com/48047773/193195102-611e309e-39ac-44f6-93a0-8a52d4de4a44.png">

<img width="743" alt="스크린샷 2022-09-16 오후 5 40 56" src="https://user-images.githubusercontent.com/48047773/193195112-556e2040-e190-427a-a0a5-5ba88cd51c3f.png">
