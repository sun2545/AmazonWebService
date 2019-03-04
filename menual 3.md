     https://youtu.be/WH1VZvkje0Y
     
     
     
   ~ EB CLI (Elastic Beanstalk Command Line Interface) 설치해야 AWS를 제대로 편리하게 사용할 수 있음
     - 우선 Python을 설치해야함 (다운로드 후 설치시 'Add Pythone 3.6 to PATH' 체크박스를 체크하고 설치해야함

     - Install the Elastic Beanstalk Command Line Interface (EB CLI) 설치 안내 페이지
       ~ https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html?icmpid=docs_elasticbeanstalk_console

     - Python 설치후 도스창(Command Line)
       ~ C:> $ pip install awsebcli --upgrade --user

       - Windows PATH에 추가: Python 3.6 – %USERPROFILE%\AppData\Roaming\Python\Python36\Scripts
       - 입력방법: 윈도우키 > env > 계정의 환경 변수 편집 > Path

     - 로컬컴퓨터와 AWS와 연결을 해줘야 함 (폴더끼리)

     - Git 설치해야함
     - Git 설치후 클론 (Git에서 로컬로 다운로드)
     - https://github.com/hotdeveloper/secret-memo-backend
     -> git clone http... (백엔드 주소)
     -> git clone http... (프론트엔드 주소)

     -> eb init  (엘라스틴 빈스토크를 사용하겠다는 것을 알림)
     -> 원하는 애플리케이션 번호 선택: ex) 1) aws-1st-app
     -> 아이디/비밀번호 입력
       ~  내 보안 자격 증명 > 액세스 키(엑세스 키 ID 및 비밀 액세스 키) 메뉴에서 새로 액세스키를 만들어야 함

     -> eb deploy (로컬 내용을 AWS 서버로 업로드 하는 명령어)

     -> 샘플코드는 express.js 로 만듦 (app.js 에서 시작됨)
       ~ 대부분의 코드는 프레임웤에서 자동으로 만들어진 코드임
       ~ ex) mysql 접속 관련 코드
                var mysql = require('mysql');
                app.use((req, res, next) -> {
                    res.locals.connection = mysql.createConnection({
                        host: 'localhost',
                        user: 'user',
                        password: '12345',
                        port: '3306',
                     });
                 });

   ~ 여러가지 프레임웤을 사용하는 경우는 'app.js'라는 이름을 여러 프레임웤에서 사용할 수 있기 때문에
      app.js -> 다른 이름으로 (main.js) 바꿔줘야 함

   ~ experess 는 bin/www [웹서버]에서 설정을 함
    ex) 변경전: var app = require('../main');
     ex) 변경후: var app = require('../main');

   ~ react, express 등 각각 Web 서버를 가지고 있음

     -> 파일 '.aws' 라는 폴더의 config 파일에 '액세스 키 ID'와 '보안 액세스 키'가 저장됨

     -> eb deploy 명령 입력하면 depoly 됨
       - 필요파일(폴더)전체 압축후 업로드 진행됨
       - 정상적으로 올라가면 'AWS' 모니터링 메뉴에 가면 현재 상태를 볼 수 있음

     -> 'S3'는 아마존의 파일 저장해주는 서비스

   ~ 로컬에서 Front End
     - npm 사용해서 frond end 테스트: localhost:3000
     - node로 구동될 때 index.js 가 로딩되고 index.js는 app.js를 구동시킴

   ~ 처음 git에서 다운로드 후에는 'npm install'을 한번 해줘야 함
     - npm audited 등 알림이 나올 경우 절대로 신행하지 말것 (실행에 중요한 부분을 자동으로 고쳐서 동작이 안됨)
     - 'npm intall'을 하지 않고 npm start 를 할경우 처음에는 안됨

   ~ npm run build 명령
     - 로컬에서 설치된 항목들이 '서버'에 배포할 경우 제대로 동작하지 않는 경우가 많음
     - 그래서 필요함
     - 다른 웹서버에서 돌리기 편하게 해줌 (Webpack 이라는 툴을 사용함)
     - 컴퍼일러(트랜드파일러) 비슷한 개념
     - 클라이언트의 /build/static/js/ 폴더에 암호화(읽기 힘든 상태)로 변형된 파일이 생성됨
     - 해당파일을 복사해서 '백엔드'의 'public' 폴더에 붙여넣기 하고나서 바로는 동작 안되고
     - 백엔드에서 'eb deploy' 명령을 치면 새로운 파일을 추가해서 배포가 됨
     - AWS 서버의 대시보드에서 업데이트 및 완료 상태 확인 가능
     - deploy 완료후 AWS 의 서버에서 제대로 반영되었는지 확인 해보면 됨

   ~ Client
     - package.json 파일에서 'Bacnend'의 주소를 고쳐줘야함
       예) "proxy": "http://aws1stapp-env.3qbqm2ej4c.us-......." (AWS 애플리케이션의 주소)

    - 요약
     ~ 파이썬 설치
     ~ eb cli 설치
     ~ Git 설치후 클론으로 '백엔드', '프론트엔드' 파일 다운로드

     ~ 백엔드 eb init 연결 (서버 지역, 암호등)
     ~ npm 돌려서 설치 후 몇가지 수정
     ~ eb deploy

     ~클리이언트 수정 (public 폴더)
     ~ 다시 eb deply
     ~ 문제점 확인
docs.aws.amazon.com
Install the Elastic Beanstalk Command Line Interface (EB CLI) - AWS Elastic Beanstalk
Step-by-step installation of the Elastic Beanstalk Command Line Interface (EB CLI).
GitHub
hotdeveloper/secret-memo-backend
Contribute to hotdeveloper/secret-memo-backend development by creating an account on GitHub.
