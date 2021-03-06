# GNSS
  
 : 진행한 GNSS 관련 프로젝트의 코드를 정리합니다.
     
#### 🚩RTK(Real Time Kinematic)란 무엇인가?
 >  높은 수준의 정확도를 확보하기 위해 후처리가 필요했던 기존 측량 방식과는 다르게, 네트워크를 통해 기준국으로부터 실시간으로 보정정보를 수신하여 cm 단위의 정확도를 확보하는 측량기술. RTK 수신기를 통하여 실시간으로 높은 정확도의 위치정보를 얻을 수 있다.
   
---
  
### 🌏eqrthquake_POHG
 >  2011년 동일본 대지진 발생 이후 GNSS 데이터를 통해 판의 이동을 감지한 여러 논문들을 참고하여, 17년 11월 발생한 포항 대지진 이후 비슷한 양상이 있었는지 후처리 RINEX 데이터를 종합하여 판단하고자 하였다.
 >    
 >>1. 대상 기준국 및 연도
 >>    * 2017~2018년, 총 2년간의 30분 간격 RINEX 데이터를 사용
 >>    * 보현, 호미, 군위, 부산의 네 기준국을 기준으로 하였음
 >>2. 사용 데이터
 >>    + RTKLIB을 통하여 추출한 결과 데이터 중, Q값이 1인 신뢰성 높은 자료들만 사용함
 >>    + 군위의 경우 17년 10월경의 관측소 데이터가 존재하지 않는다.  
 
### 🌏trans_coordinate
 >  Ellipsoidal 좌표계와 ECEF 좌표계 간의 변환, ECEF좌표계와 ENU 좌표계 간의 변환을 지원한다.  

### 🌏true_position
 >  위의 좌표 변환 코드에서 ECEF->ENU 를 활용해, 측정 데이터와 실제 데이터를 rms값을 통해 비교할 수 있다. 결과 데이터의 신뢰성을 이를 통해 판단한다.
