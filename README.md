
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
  
  ### 5.[마이페이지](#myPage-anchor)
   #### - [자주 구매한 상품](#frequently-purchased-product-anchor)
   #### - [주문확정](#order-confirm-anchor)
   #### - [환불하기](#order-refund-anchor)
   #### - [리뷰작성](#review-anchor)
 
 
 ### 6.[판매자](#seller-anchor)
  #### - [회원가입](#seller-register-anchor)
  #### - [상품등록](#seller-productRegister-anchor)
  #### - [판매자 페이지](#sellerPage-anchor)


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


<a name="myPage-anchor"></a>
## 마이페이지

<a name="frequently-purchased-product-anchor"></a>
### 자주 구매한 상품


마이페이지에서 자신이 자주 구매한 상품을 top5로 확인하실 수 있습니다.

![image](https://github.com/user-attachments/assets/416dda48-8076-4324-bffa-ce273f0f4ba0)


![image](https://github.com/user-attachments/assets/6bd0ddd6-03cd-4c43-b50e-f00e1d1694b5)


<a name="order-confirm-anchor"></a>
### 주문확정


주문확정을 하실 경우

일반회원 - 구매금액의 1% 포인트 적립

멤버쉽회원 - 구매금액의 5% 포인트 적립


주문확정을 하면 제품의 문제가 있지않고 단순 변심의 경우 환불이 불가능합니다.


 - 일반회원일 경우

![image](https://github.com/user-attachments/assets/f6d305c8-ca66-4c7b-9c8d-2140cc03fc85)


![image](https://github.com/user-attachments/assets/fc60ceda-64f6-418c-bf1b-125c7582b35d)


![image](https://github.com/user-attachments/assets/9da40e98-26ac-4899-b9e4-78a146548a17)


 - 멤버쉽 회원일 경우


![image](https://github.com/user-attachments/assets/768a2e8a-e000-4c09-8c42-30c45f9cbfef)


![image](https://github.com/user-attachments/assets/65b59e00-bae4-41ea-b34c-32dd009445e7)


![image](https://github.com/user-attachments/assets/b76a5874-812b-45f8-96fd-d198cfaeb95f)


<a name="order-refund-anchor">
 
### 환불하기

환불하기 버튼을 눌렀을 경우에는 구매한 금액과 사용한쿠폰+포인트 금액을 환불 받을 수 있습니다.


![image](https://github.com/user-attachments/assets/903a2b77-762d-4f92-be29-4f6010b82732)


![image](https://github.com/user-attachments/assets/80dc11e3-d5a3-4cb2-a497-2a4733d982c7)


![image](https://github.com/user-attachments/assets/34f31d42-70b9-4142-b77b-c7986828e7fa)


<a name="review-anchor">
 
### 리뷰작성

배송이완료되고 주문확정을 하였을 경우 마이페이지 상품후기에 리뷰를 작성할 수 있습니다.

- 글후기 50원

- 사진후기 100원

- 멤버쉽회원일 경우 포인트적립 2배 적용


일반회원일 경우


모달창으로 열리게 해놓았으며 후기에 별점을 부여할 수 있고 사진도 등록이 가능합니다.


![image](https://github.com/user-attachments/assets/c240ec96-3859-4666-8413-a654be5ba2aa)


![image](https://github.com/user-attachments/assets/0dcb19c4-235c-40b0-9e84-c7973c6ed1f3)


후기를 작성하고 50포인트가 적립된것을 확인하실 수 있습니다.


![image](https://github.com/user-attachments/assets/29bba204-3290-4440-8cdd-47310e32d786)


![image](https://github.com/user-attachments/assets/8405aacb-4b67-477e-9fd9-d0f943ac9722)


![image](https://github.com/user-attachments/assets/d8243f4d-5ce7-4fdd-b047-0b946c162485)


사진을 포함하여 후기를 남길 시 100포인트가 적립된것을 확인하실 수 있습니다.


작성완료 후기에서 자신이 작성한 후기를 확인하실 수 있습니다.


![image](https://github.com/user-attachments/assets/febe00d1-1774-487a-9ce8-3ebb911ddfe4)


멤버쉽 회원일 경우 멤버쉽 혜택으로 2배 적용되어 글 후기는 100원 사진후기는 200원이 적립이 됩니다.

![image](https://github.com/user-attachments/assets/486bc46b-9af6-48d1-93c5-266a1c448c8b)


![image](https://github.com/user-attachments/assets/abd01288-f222-41a7-88b3-528759928cd8)


![image](https://github.com/user-attachments/assets/8a423678-3762-44cc-bf41-9b7269abcf6e)


![image](https://github.com/user-attachments/assets/1acdfeaf-f520-41c9-b512-58e744b6e6c7)


상품의 하단에 고객들이 적은 후기의 개수를 확인할 수 있습니다.


![image](https://github.com/user-attachments/assets/dffb4766-bbea-4170-a632-a7f4ad3543dc)


상세페이지에서도 리뷰의 개수와 별점의 평균, 작성한 리뷰 목록을 확인할 수 있습니다.


![image](https://github.com/user-attachments/assets/7dbbaa82-36b4-4c42-9a26-3b501c17cd0e)


![image](https://github.com/user-attachments/assets/7f518098-7b6e-4c6e-8757-b9d3a53fbf47)


<a name="seller-anchor"></a>
## 판매자

<a name="seller-register-anchor"></a>
### 회원가입

우측에 회원가입을 누르면 개인회원가 사업자 회원으로 가입을 선택하실 수 있습니다.


![image](https://github.com/user-attachments/assets/5129dd96-e1a6-4b0a-966d-476569194b19)


![image](https://github.com/user-attachments/assets/abc51a4d-5df9-4571-92e3-cadb92aa4c28)


![image](https://github.com/user-attachments/assets/9e04d767-a2f2-4a23-982e-7ba5ee9a64cd)


로그인시 고객, 판매자 중 선택하여 로그인 하실 수 있습니다.


![image](https://github.com/user-attachments/assets/ab5b82de-fb8e-48b6-a16b-8649ce28a712)


![image](https://github.com/user-attachments/assets/e4aa2ba4-44b9-4ef3-8b45-9c2b39fb1979)


<a name="seller-productRegister-anchor"></a>
### 상품등록


우측 상단 자신의 닉네임을 클릭하면 판매자페이지로 진입합니다.


![image](https://github.com/user-attachments/assets/a8eec5b7-878b-4889-81a2-5a8ff659d323)


우측 중간에 상품 등록하기를 클릭하면 상품등록 페이지로 이동하여 상품을 등록하실 수 있습니다.


![image](https://github.com/user-attachments/assets/5201218d-f8b7-4273-8104-72ac1ea0e653)


![image](https://github.com/user-attachments/assets/737be582-5e05-42fd-8f9b-4bbe3198e67e)


![image](https://github.com/user-attachments/assets/b40a73dd-45f4-4fd3-b47e-ffbdea9096d9)


상품을 등록 시 고객들이 상품을 구매할 수 있습니다.


![image](https://github.com/user-attachments/assets/fdac0216-8ff0-47cf-b5c5-daa4a908a925)


![image](https://github.com/user-attachments/assets/d86ee3c0-81a0-4aa0-b9ce-39003f2f9586)


<a name="sellerPage-anchor"></a>
### 판매자페이지


상품의 기존가를 기존가 변경을 통해 변경하실 수 있습니다.


![image](https://github.com/user-attachments/assets/6b850c35-0936-4c80-b16d-7aec53560f6c)


![image](https://github.com/user-attachments/assets/aa7a097c-ead2-4762-a9ca-66efc12731de)


상품의 수량을 수량 추가를 통해 수량을 추가하실 수 있습니다.


![image](https://github.com/user-attachments/assets/5b0e48c7-efd7-44bc-bac7-b9bf6dd0abfa)


![image](https://github.com/user-attachments/assets/6f8591f9-4ee5-490f-9985-bf0ecfbbc6fd)


상품의 할인율을 할인율 변경을 통해 할일율을 조정하실 수 있습니다.


![image](https://github.com/user-attachments/assets/920e0454-0a22-4630-abf1-5a49ff8add7b)


![image](https://github.com/user-attachments/assets/949cc081-259d-4afd-9c98-1de5d1e1d30e)


고객이 해당 상품을 구매했을 경우 누적 판매량이 증가합니다.


![image](https://github.com/user-attachments/assets/658186ee-cb16-49df-b8d0-07187bafc9cb)


![image](https://github.com/user-attachments/assets/b85c9fef-c58e-4b97-afc5-a3e4d6b3dd9a)





































































































































































































