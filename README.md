# Portfolio Sample
Sample Developer Portfolio for Job Seekers and Career Changers


# 인프런 강의

<img src="https://github.com/villainscode/DesignPattern/blob/main/image/inflean_code.jpeg" width="1000">

- [시니어면접관이 알려주는 개발자 취업과 이직, 한방에 해결하기 이론편](https://www.inflearn.com/course/%EC%8B%9C%EB%8B%88%EC%96%B4-%EB%A9%B4%EC%A0%91%EA%B4%80-%EC%95%8C%EB%A0%A4%EC%A3%BC%EB%8A%94-%EC%B7%A8%EC%97%85-%EC%9D%B4%EC%A7%81-%EC%9D%B4%EB%A1%A0)
- [시니어면접관이 알려주는 개발자 취업과 이직, 한방에 해결하기 실전편](https://www.inflearn.com/course/%EC%8B%9C%EB%8B%88%EC%96%B4-%EB%A9%B4%EC%A0%91%EA%B4%80-%EC%95%8C%EB%A0%A4%EC%A3%BC%EB%8A%94-%EC%B7%A8%EC%97%85-%EC%9D%B4%EC%A7%81-%EC%8B%A4%EC%A0%84)




## 프로젝트 목표
사내 각 서비스들마다 흩어져서 구현하던 메시지 전송 기능을 연동 플랫폼과 전송 미들웨어를 통합하여 제공하고 다양한 포맷을 지원한다. 

- 사내 메시지 발송기를 통합하여 여러 부서에 파편화된 리소스를 공통 플랫폼으로 전환하여 효율화 <br> 
- 메시지 중요도와 발송량에 따라 기존 장비를 활용하고 고속, 고용량의 경우 고사양 장비 활용 <br>
- 다양한 포멧의 메시지를 지원하여 대외로 나가는 모든 메시징 통합 <br>

### 기대효과 
>
>운영 리소스 50% 감소 및 메시지 발송 증가에 따른 발송 지연 CS 비용 해소<br>
>모든 인입 메시지를 트레킹하고 메시지 유실 관리 기능 제공<br>
>대외로 나가는 모든 메시지를 통합 관리 가능<br>
>

## 아키텍처

<img src="./image/notification.png" width="1200">

## 개발 스택
> JDK 1.8, SpringBoot 3.x <br> 
> Elasticsearch 8.x,  Kafka 3.x, Redis 7.x, RabbitMQ 3.10.x, MongoDB 6.x 


## 핵심 기능 
>
>전체 발송 메시징 적재 후 retryable 처리, 실패시 메뉴얼 발송 가능 <br>
> 메시지 가중치 스펙 도입, 메시지 타입 및 조건에 따라 처리 성능별 Producer 분배 <br>
> Redis Pub/Sub 을 이용한 웹 알림 View Plugin 모듈 제공 (재개발 필요없이 CSS만 수정하여 커스텀) <br>
> 메시지 전송과 서비스 비즈니스의 격리, 발송 규격 및 메시지 팀플릿 등록 후 인하우스 유저가 권한 획득하여 발송 <br>
> 발송 히스토리는 관리자 화면에서 실시간으로 확인
> 각 레이어별로 이벤트 수집, 정제, 메시지 가공, 발송, 결과 수집 기능 구현
