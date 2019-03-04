     MySQL Workbench 로 AWS RDS MySQL 접속과 테이블 작성
https://www.youtube.com/watch?v=VaaEpTaJpHY 
https://youtu.be/eANRvLs-siI


     - docs.aws.amazon.com > 자습서 및 프로젝트
       ~ 프로젝트 안내서 시작하기

     - 다운로드할 것: eb-node-express-sample-v1.1.zip
       ~ Node 프로그램
         - 포함: load balancer => High availability
           ~ 라운드 로빈 (순차적으로 1,2,,,N, 1, 2...),
           ~ 다른 방식 (서버 상태 확인후 가능한 서버로 연결)

     - 사용서비스: Elastic Beanstalk

     - UnxUtils : Windows 에서 유닉스 명령어를 사용할 수 있게 해주는 프로그램

     - 참고
       ~ AWS 비용: 서버 사용시간만큼만 비용 지불
       ~ 웹앱 생성 다른방법: 기본 웹 앱 생성: 간단한 (기본) 기능: '콘솔에 로그인' 메뉴

     - 콘솔(Console에 로그인)
       ~ 링크클릭하여 디폴트 서비스들을 선택하여 앱생성 (클라우드에 서버 생성)
         - 플랫폼: Node.js 선택

       ~ 앱생성 클릭 (3~5분 시간 소요): Turotials-env 생성 (가상서버[인스턴스] 생성)
         - 화면에 설지 항목 및 시간 표시 (한국어 지원이 많이 늘어남)
       ~ 완료 후 '대시보드' 메뉴 표시 (서버 및 서비스 상태)

     - 다운로드 받은 파일 (eb-node-express-sample-v1.1.zip)
       ~ 관리페이지 이동
       ~ 선택후 업로드 및 배포: zip 파일을 직접 선택
       ~ 압축파일: DB 생성 및 테이블 생성 파일, Java script 어플리케이션 파일 (Node.js, Express)
       ~ 업로드 및 기능 완료 후 내용중 상단의 접속 URL 클릭하면 웹브라우저에서 확인 가능함
         - 예) tutorial-env.2uxn4fz3md.us-east-2.elasticbeanstalk.com
       ~ 압축파일(eb-node-express-sample-v1.1.zip) 구성
         - app.js
         - iam-policy.json
         - ...

     - 각 파일별로 필요한 내용 변경한다음 압축해서 다시 업로드 하면 새로 변경된 내용 배포됨
       ~ 압축파일 내용 수정
       ~ 다시 압축후 업로드

   - 오늘 올린 파일은 아마존에서 테스트용으로 제공한 샘플 앱
     ~ app.js (파일 소스 내용 참고로 확인)
       - 앱 기능 포함
       - DB 접속 관련: 다이나모 DB 접속
       - render(index) : /views/index.ejs (static html) 파일 표시

   - DB 확인 하는 방법
     ~ DB 콘솔 (DB 관리 화면: phpMyAdmin 비슷한 관리 화면)
     ~ DynamoDB
     ~ 웹페이지에서 'Sign up today' 하면 해당 테이블에서 데이터 항목 추가된 것 확인 가능

   - 권한 관련 (zip 파일에 이미 포함됨)
     ~ Dynamo DB 접근 권한 등 설정
     ~ SNS 관련 권한

   - 고가용성 환경 구성
     ~ 1. Elastic Beanstalk 콘솔
     ~ 2. 해당 관리페이지 이동
     ~ 3. ... 인스턴스 2개 이상... 선택 ...

   - '모니터링' 메뉴
     ~ 사용량, 예상 비용

   - 숙제
     ~ 개인별로 실습 후 잘 돌아가는 URL을 슬랙 (#general) 에 업로드
     ~ 대시보드 메뉴 상단의
       - 환경 ID: e-erwrwrewr, URL: tutorial-env.2uxn4fz3md.us-east-2.elasticbeanstalk.com
     ~ Due Date: 1월 29일 화요일까지

 
   ~ 질문: 업로드 파일 내부의 index.ejs (ejs 확장자)
   ~ 답변:
     - html (php의 html 템플릿과 비슷한 기능)
     - html과 JQuery(Javascript)를 이용해서 Ajax 등을 이용해서 명령 기능을 수행함.
       예) app.post('/signup', function(req, res) {
                 // code...
             }
     
