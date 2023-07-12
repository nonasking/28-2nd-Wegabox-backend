# 28-2nd-Wegabox-backend
- [**Megabox**](https://www.megabox.co.kr/)는 영화 예매 사이트입니다.
- 사이트의 핵심 기능인 영화 정보 조회 및 예매 기능을 중심으로 구현하였습니다.

</br>

## 개발인원 및 기간
- 개발기간 : 2022-01-10 ~ 2022-01-21
- Front-end : [Wegabox 프론트엔드 github repository 링크](https://github.com/wecode-bootcamp-korea/28-2nd-Wegabox-frontend)
- Back-end : 강민성, 장민욱

</br>


## 시연 영상
- [시연 영상 다운로드 링크](https://drive.google.com/file/d/1VEoUUSFTfd--QTRzeEnlRnOCLVZ2fl57/view?usp=sharing)
- [Wegabox 프로젝트 링크 바로가기](http://54.144.54.249:8000)

</br>


## 협업 도구
- Slack
- Github
- Trello

</br>


## 기술 스택
- Language: Python3
- Framework: Django
- Database: MySQL
- Infra: AWS(EC2), RDS

</br>


## ERD
핵심 기능 중심으로 compact하게 구현
![모델링](https://user-images.githubusercontent.com/83395303/150482436-918b12f6-6c04-47f0-a4ca-2ca22c7eaa6a.png)

</br>


## 구현 기능
### 강민성
소셜로그인, 예매

</br>


#### User
##### 소셜로그인(카카오)
- 프론트에서 받은 access_token을 카카오 API에 요청하여 유저 정보 조회
- 조회한 유저 정보가 DB에 있는지 확인하고 get_or_create로 DB에 유저를 등록하거나, 이미 등록되어있다면 기존의 유저 정보를 가져오기
- 유저의 PK(Primary Key)를 payload로 하여 jwt 토큰 생성
- login decorator : jwt 토큰을 복호화하는 데코레이터를 구현하여 로그인이 필요할 때 사용

</br>


#### Ticketing
##### 예매
- Q객체를 활용하여 사용자가 선택한 옵션(상영일, 영화, 지역, 극장)에 따라 서로 다른 데이터가 필터링되어 프론트로 리턴
- 상영 스케줄을 선택하면 데코레이터를 통해 받아온 유저 id와, 유저가 선택한 스케줄 id로 예매 데이터를 생성 

</br>


### 장민욱
메인 및 영화 리스트 페이지, AWS

</br>


#### Movie
- 사용자가 전체 영화 리스트 또는 개봉작만 보도록 Q 객체를 활용
- annotate를 활용하여 테이블에 예매율을 계산한 칼럼 추가, 영화관에서 상영 중인 영화 목록을 예매율 내림차순으로 볼 수 있도록 구현

</br>


#### AWS (EC2, RDS)
- EC2, RDS 세팅하여 배포 완료
- 데몬을 통한 서비스 백그라운드 실행

</br>


## Reference
- 이 프로젝트는 [**Megabox**](https://www.megabox.co.kr/) 사이트를 참조하여 학습목적으로 만들었습니다.
- 실무 수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제가 될 수 있습니다.
- 이 프로젝트에서 사용하고 있는 사진 대부분은 위코드에서 구매한 것이므로 해당 프로젝트 외부인이 사용할 수 없습니다.
