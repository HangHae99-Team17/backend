![image](https://user-images.githubusercontent.com/90609214/144568268-40e390ec-ac72-478d-a4de-97cc584e557e.png)
 
# 주요기능 아키텍처
![image](https://user-images.githubusercontent.com/90609214/144568667-2a0749ca-d04c-4606-8aa2-9dcb98e77eb3.png)

* Create

Admin이 create요청을 하게되면 입력한 값 중 이미지파일은 s3에 저장되고, s3에서는 저장된 이미지의 url을 서버에 보내줍니다. 이 이미지 url은 보내진 다른 값들과 함께 MYSQL에 저장됩니다. 
* Update

Admind이 update요청할때는 MYSQL에 원래 존재하는 데이터들을 업데이트 해주고 이미지파일은 S3에서 원래있던 사진을 삭제하고 저장됩니다. 그리고 s3에서 url을 가져와 기존사진 url을 업테이트합니다.
* Delete

Admin이 삭제요청하면 S3에있는 이미지 파일과 함께 DB안에 데이터를 삭제합니다. 
* Read

User가 read요청을 하게되면, 서버는 MYSQL에 저장되어 있던 데이터들을 불러와 프론트로 응답해줍니다. 서버에서 보내준 이미지URL은 프론트에서 이미지화 시켜 보여줍니다.

 
 
# 백엔드 배포 파이프라인

![image](https://user-images.githubusercontent.com/90609214/144567611-a6a55e77-efe4-4ee2-9166-4372f80618b9.png)

인텔리제이에서 깃헙에 올리고 깃헙에서 액션으로 s3와 codeDeploy를 이용하여 자동적으로 통합하고 배포를 합니다. 그리고 엔진엑스를 이용하여 로드밸런싱, 무중단배포, HTTPS를 적용하려고 했는데 현재 11월 30일기준 HTTPS만 적용되어있는 상태입니다. 



# ERD
![image](https://user-images.githubusercontent.com/90609214/144567537-b1537ae6-6cdd-43c0-a29f-2f7a12cc3432.png)


쿠폰이라는 객체는 브랜드, 설명, 등등 할인정보들의 정보와 그 할인정보의 디테일들을 가져옵니다.  

유저는 가입하는 유저들의 정보와 디테일을 가져와서 저장합니다 . 

폴더는 유저가 쿠폰을 찜한 내역과 기록을 저장하는 객체로서 유저와 쿠폰의 키값을 외래키로 가져와서 저장합니다.

# 기술스택

* Back-end

Java 8, SpringBoot 2.5.2, Spring Security, Gradle 7.0.2, JPA, MySQL 8.0

* DevOps

github Action, Nginx, AWS EC2 (Ubuntu 18.04), AWS RDS (MySQL 8.0), AWS S3, AWS codeDeploy


# Future Work

 1. 수정 자동화 (크롤링? or html파싱?)
 2. 로드밸런싱 
 3. 무중단배포
 4. 이메일 인증 
 5. 스웨거
 6. 알림기능(소켓)
 7. 소셜로그인 
 
    
