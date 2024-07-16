
프로젝트명 : 미드나잇마켓 (온라인 쇼핑몰)
========================================

개발 일정 : 2024.05.20 ~ 2024.06.24 (5주)
-----------------------------------------

## 목차


 ### 1.[멤버쉽](#membership-anchor)
  ####  - [가입](#membership-join-anchor)


###  2.[상품](#product-anchor)
 #### - [찜하기](#product-pick-anchor)
  
### 장바구니
  ####  - 추가
  ####  - 삭제

  
 ### 결제
 
  
  ### 판매자
 
  
  ### 상품 후기
 
 
 ### 멤버십, 쿠폰
 
 
 ### 주문서


# 내가 구현한 기능


<a name="membership-anchor"></a>
## 멤버쉽
<a name="membership-join-anchor"></a>
#### 가입


좌측 멤버쉽 배너를 클릭시 멤버쉽을 가입할 수 있습니다. 
![image](https://github.com/user-attachments/assets/8d5fc9b2-06ae-4555-bbc3-30b450645d68)


만약 로그인을 하지 않았을 경우 (customerId ==null) 가입 하지 못하도록 alert창으로 못들어가게 막아 놓았습니다.
![image](https://github.com/user-attachments/assets/a8a34f03-5973-4a81-a990-6c9133fbd60b)


![image](https://github.com/user-attachments/assets/b771493d-f6fd-420b-8b5d-ee26d5ed6956)


로그인을 하였을 경우에는 배너를 클릭 시 팝업창으로 멤버쉽가입 페이지가 열리며 멤버쉽을 가입할 수 있습니다.
![image](https://github.com/user-attachments/assets/245a3613-4071-4e65-93d6-db3ad4d2f8a7)


결제는 포트원 API을 사용하였고 PG사는 KG이니시스 PG사를 사용 하였습니다.
![image](https://github.com/user-attachments/assets/46852a17-2bbf-4a28-90de-bb23cd2d1f1d)


결제를 완료하였을 경우 


 - 메인페이지 우측 상단에 멤버쉽 아이콘이 활성화 됩니다.


![image](https://github.com/user-attachments/assets/5aa518f2-976f-44ae-8d14-2db0055ebcf3)


 - 마이페이지 좌측 상단에도 멤버쉽 아이콘이 활성화 됩니다.


![image](https://github.com/user-attachments/assets/48fd4d3c-382b-4b1c-b495-ae1150505da8)



 - 3000원 쿠폰 3장이 발급되어 사용할 수 있게 됩니다.


![image](https://github.com/user-attachments/assets/e8510a40-c65b-4532-b225-312b02508f71)


<a name="product-anchor"></a>
## 상품
<a name="product-pick-anchor"></a>
#### 찜하기


상품 상세페이지에 찜하기(하트 아이콘)를 클릭 시 찜하기를 할 수 있습니다.


![image](https://github.com/user-attachments/assets/a329685a-bbf9-41da-b820-0d685d46736e)


































