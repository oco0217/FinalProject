
프로젝트명 : 미드나잇마켓 (온라인 쇼핑몰)
========================================

개발 일정 : 2024.05.20 ~ 2024.06.24 (5주)
-----------------------------------------

## 기능 목차


 ### 1.[멤버쉽](#membership-anchor)
  ####  - [가입](#membership-join-anchor)


###  2.[상품](#product-anchor)
 #### - [찜하기](#product-pick-anchor)
 #### - [수량변경](#product-changeQuantity-anchor)
  
### 3.[장바구니](#basket-anchor)
  ####  - [담기](#basket-add-anchor)
  ####  - [수량변경](#basket-changeQuantity-anchor)
  ####  - [삭제](#basket-delete-anchor)
  
  ### 4.[주문서](#orders-anchor)
  #### - [주문](#order-anchor)
  #### - [쿠폰사용](#orders-coupon-anchor)
  #### - [포인트사용](#orders-point-anchor)
  #### - [결제](#orders-payment-anchor)
  
  ### 마이페이지
   #### - 자주 구매한 상품
   #### - 주문확정
   #### - 환불하기
   #### - 리뷰작성
 
 
 ### 판매자
  #### - 회원가입
  #### - 상품등록
  #### - 판매자 페이지


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


비로그인시 찜하기를 할 수 없습니다.


![image](https://github.com/user-attachments/assets/58942eac-8615-4a0a-af9e-2ee49c55beb6)



상품 상세페이지에 찜하기(하트 아이콘)를 클릭 시 찜하기를 할 수 있습니다.


![image](https://github.com/user-attachments/assets/a329685a-bbf9-41da-b820-0d685d46736e)


찜한상품을 다시 누를 시 찜한 상품이 삭제 됩니다.


![image](https://github.com/user-attachments/assets/08dd2f46-a707-40ca-8fb7-0dfcaf08defc)



내가 찜한상품은 마이페이지 -> 찜한상품 에서 확인이 가능하며 찜한 상품을 마이페이지에서도 찜한상품을 삭제하실 수 있습니다.

![image](https://github.com/user-attachments/assets/4a23c7f2-9fb6-4dee-897c-806c77c2b295)


<a name="product-changeQuantity-anchor"></a>
#### 수량변경


상품이 품절일 경우 alert로 품절을 안내하고 다음으로 못넘어가게 막습니다.


![image](https://github.com/user-attachments/assets/5bb6cad1-519d-43e2-b3f8-26ef9c381e01)



수량은 1이상만 주문이 가능합니다.


![image](https://github.com/user-attachments/assets/5534494a-f3be-4f3e-904e-eb7c5b0bb235)

주문 또는 장바구니에 담을 수량을 - + 로 조절이 가능합니다.


![image](https://github.com/user-attachments/assets/0e68605e-9382-49d0-a6f9-44dbb9e34abe)


주문, 장바구니를 클릭 시 비동기로 DB에 현재 상품의 수량을 실시간으로  체크하여 잔여수량보다 주문수량이 많거나 재고가 없을 시에 alert창으로 다음으로 못넘어가게 막습니다.


![image](https://github.com/user-attachments/assets/49be2520-39c2-4b65-8773-b9cd1c2eaa80)


![image](https://github.com/user-attachments/assets/d712bafe-abdf-499f-ac5b-ad38f14e29e0)



주문 또는 장바구니에 담을 상품의 수량이 품절일 경우 (total_qty == 0) 주문이나 장바구니에 담지 못합니다.


![image](https://github.com/user-attachments/assets/3c53d738-2a8f-4095-a41c-c565845192e7)


![image](https://github.com/user-attachments/assets/34aa58c2-f502-435d-af65-0d9617d01e1f)


주문 또는 장바구니에 담을 상품의 수량이 현재 상품의 잔여수량보다 많이 주문할 경우

alert 창으로 현재남은 잔여수량에 대해 알려주고 주문할지 말지 결정할 수 있습니다.


![image](https://github.com/user-attachments/assets/ef19c3ab-1059-48d8-865f-aa589f03e543)


![image](https://github.com/user-attachments/assets/06eafdc6-07a6-4504-94e2-ce55c14e570d)


<a name="basket-anchor"></a>
## 장바구니
<a name="basket-add-anchor"></a>
### 담기

메인 페이지에서 상품을 장바구니에 담을 수 있습니다.


![image](https://github.com/user-attachments/assets/6ed5bcf9-544c-42c8-bd53-e97c9d2a99c4)


상품이 품점되었을 경우에는 장바구니에 담을 수 없습니다.


![image](https://github.com/user-attachments/assets/33409dc7-6c17-4679-b0af-90991be424d8)



상품 상세 페이지에서도 원하는 갯수만큼 장바구니를 담을 수 있습니다.


![image](https://github.com/user-attachments/assets/5779ead4-dea3-4300-a9d5-3d058f30ff29)


![image](https://github.com/user-attachments/assets/27a77320-5ca2-4592-9a72-9575eac51811)


<a name="basket-changeQuantity-anchor"></a>
### 수량변경


수량을 - + 로 장바구니로 주문할 수량을 변경할 수 있습니다.


![image](https://github.com/user-attachments/assets/78ac840f-2cae-4555-8d05-df896bf32bd3)


장바구니에 담긴 수량이 현재 상품의 잔여수량보다 많을 경우 장바구니 주문을 막고 현재 상품의 최대 수량만큼 변경이 됩니다.


![image](https://github.com/user-attachments/assets/f9d634ff-df77-4f63-a316-d690c947409a)


![image](https://github.com/user-attachments/assets/097947f0-a023-4d66-923f-8e7195928d13)


유기농 양파의 수량이 변경된 것을 확인하실 수 있습니다.


![image](https://github.com/user-attachments/assets/a9bb8286-fd50-493c-a68f-c1ae6f8f7a93)


<a name="basket-delete-anchor"></a>
### 삭제


상품의 좌측에 체크박스를 통하여 자기가 원하는 상품들만 주문하거나 삭제를 할 수 있습니다.


![image](https://github.com/user-attachments/assets/f68aa6f2-374e-40ec-b683-8d226d86bfe4)


<a name="orders-anchor"></a>
## 주문서
<a name="order-anchor"></a>
### 주문

상품 상세페이지 또는 장바구니에서 주문을 하실 수 있습니다.

![image](https://github.com/user-attachments/assets/1d1eb79f-d7f0-41cb-b4e1-e52214f03b1d)


아코디언을 통해 자신이 주문할 상품들의 정보를 열고 닫을 수 있습니다.


![image](https://github.com/user-attachments/assets/34f07444-c0d8-48ef-b346-7536396b5e60)


![image](https://github.com/user-attachments/assets/0dbd6d58-a581-40ac-9fc0-23e66d18a1b7)


<a name="orders-coupon-anchor"></a>
### 쿠폰사용


쿠폰선택을 눌러 쿠폰을 사용할 수 있습니다.


![image](https://github.com/user-attachments/assets/402593f7-227e-45b3-9b06-a8bd72c98042)


![image](https://github.com/user-attachments/assets/238f1448-d575-4f7d-9f64-269c5245bb60)


쿠폰을 사용하면 쿠폰의 금액만큼 최종 결제금액이 할인됩니다.


![image](https://github.com/user-attachments/assets/a125715c-8802-4f7a-928a-ef0cb84e9e29)


<a name="orders-point-anchor"></a>
### 포인트사용


현재 보유한 포인트를 사용할 수 있습니다. 모두사용을 누를경우 사용가능 포인트를 모두 사용할 수 있습니다.


![image](https://github.com/user-attachments/assets/e737d504-92b5-4dbc-a5f0-b9f5f9306857)


![image](https://github.com/user-attachments/assets/39d2f90b-fc24-45ad-99d4-fe197e349dc4)


<a name="orders-payment-anchor"></a>
### 결제


결제는 포트원 API를 사용하였고 PG사는 KG이니시스를 활용하였습니다.


![image](https://github.com/user-attachments/assets/afd490ab-546a-4e22-ae7a-3d81f40259b8)


사전검증 사후검증을 통하여 금액을 변조하여 결제의 악용을 차단하였습니다.


![image](https://github.com/user-attachments/assets/a50beefc-a14f-4cc9-aa68-9ffcf519a178)


![image](https://github.com/user-attachments/assets/99f49f2b-62e5-432a-ae28-6a653e09018d)


 미리 결제할 가격을 포트원에 보내어 사전에 등록을 하여 결제창 진입시 사전에 등록한 금액과 일치하는지 확인합니다.


![image](https://github.com/user-attachments/assets/38ea339f-8372-4261-8b46-d2b9b10c29fb)


![image](https://github.com/user-attachments/assets/e675c2e4-36b2-4aa3-9a4b-4d06aa6618a3)


결제를 완료후 한번더 검증을 통하여 결제한 금액과 일치하는지 확인 후 일치하지 않다면 결제를 취소하여 사후검증을 합니다.


![image](https://github.com/user-attachments/assets/deba049c-1cda-489c-aa5f-41a38f4869ea)


결제를 성공하였을 경우 주문내역을 마이페이지에서 확인하실 수 있습니다.

주문확정을 할 경우 포인트를 적립할 수 있습니다.


![image](https://github.com/user-attachments/assets/9318d8b9-1904-4b3e-bc7e-d5777254f172)


![image](https://github.com/user-attachments/assets/bbab998f-02cc-4cd3-919c-beb6d0c06f7e)


![image](https://github.com/user-attachments/assets/239a68eb-fc9e-46f0-bb7e-d627eea0bf9c)









































































































