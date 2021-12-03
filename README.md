![image](https://user-images.githubusercontent.com/90609214/144568268-40e390ec-ac72-478d-a4de-97cc584e557e.png)
 
# 주요기능 아키텍처
![image](https://user-images.githubusercontent.com/90609214/144568667-2a0749ca-d04c-4606-8aa2-9dcb98e77eb3.png)


 
 
# 백엔드 배포 파이프라인

![image](https://user-images.githubusercontent.com/90609214/144567611-a6a55e77-efe4-4ee2-9166-4372f80618b9.png)

인텔리제이에서 깃헙에 올리고 깃헙에서 액션으로 s3와 codeDeploy를 이용하여 자동적으로 통합하고 배포를 합니다. 그리고 엔진엑스를 이용하여 로드밸런싱, 무중단배포, HTTPS를 적용하려고 했는데 현재 11월 30일기준 HTTPS만 적용되어있는 상태입니다. 



# ERD
![image](https://user-images.githubusercontent.com/90609214/144567537-b1537ae6-6cdd-43c0-a29f-2f7a12cc3432.png)


쿠폰이라는 객체는 브랜드, 설명, 등등 할인정보들의 정보와 그 할인정보의 디테일들을 가져옵니다.  

유저는 가입하는 유저들의 정보와 디테일을 가져와서 저장합니다 . 

폴더는 유저가 쿠폰을 찜한 내역과 기록을 저장하는 객체로서 유저와 쿠폰의 키값을 외래키로 가져와서 저장합니다.




 
    
