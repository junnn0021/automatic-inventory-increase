## Team F

박민혁 : [Park-Seaweed](https://github.com/Park-Seaweed) | 이준석 : [junnn0021](https://github.com/junnn0021) | 이혜정 : [hyezzang](https://github.com/hyezzang) | 
 --- | --- | --- | 

- Duration : 2022.12.23~23.12.27
<br>

## Requirement

#### 요구사항 1 : 재고부족으로 인한 구매실패에 대한 조치
Sales API 를 통해 요청을 받은 서버가 데이터베이스에서 재고 상황을 확인합니다.
재고가 있다면 감소시키고 응답으로 판매완료 내용을 전달합니다.
재고가 없는 경우 공장에 주문을 진행합니다
재고가 없다는 내용을 담은 메세지 페이로드가 주제별로 생성됩니다.
메세지가 느슨하게 연결된 시스템을 통해 처리될 수 있도록 따로 보관됩니다.

#### 요구사항 2 : 메세지 누락 상황에 대한 조치
빈번한 요청으로 메세지 누락이 발생합니다.
메세지가 처리되지 않은 경우 메세지들을 체계적으로 관리할 다른 처리 공간을 생성해야합니다.
메시지 처리 보관 리소스와 처리되지 않은 메세지 처리 리소스가 연결되어야합니다.

#### 요구사항 3 : Legacy 시스템(Factory → Warehouse) 성능문제에 대한 조치
안정적으로 이벤트가 전달 될 수 있는 시스템을 구축해야합니다.
메세지를 소비하는 리소스를 통해 Factory API가 호출됩니다.
수신된 메세지에 의해 트리거가 된 컴퓨팅 리소스가 상품 재고를 증가시킵니다.

<br>

## Summary
<p>“노티드”는 온라인으로 도넛을 판매합니다.<br />
웹사이트를 통해서 주문 버튼을 누르는 것으로 구매가 가능합니다.<br />
창고에 재고가 있다면 재고가 감소하고 구매가 완료됩니다.<br /><br />
창고에 재고가 없을 경우 구매가 불가능한 경우가 발생합니다.<br />
창고의 도넛 재고가 다 떨어지면 제조 공장에 알려서<br />
다시 창고를 채우는 시스템을 구축해야 합니다.<br /><br />
재고가 없을 경우 자동으로 제조 공장인<br />
“노티드 팩토리”에 주문을 요청할 수 있어야 합니다.<br />
주문이 요청되면 일정 시간이 지난 후 창고에 재고가 증가합니다.</p>
<br>

## Architecture

![image](https://github.com/junnn0021/automatic-inventory-increase/assets/119108967/648d7195-9638-4212-a7f4-278f028e2ff1)
- 아키텍처 구현 과정 : [Notion](https://www.notion.so/Project_Docker-K8s-df3fec7282fb4ad2883eaececfec8687)

<br>

## Environment
<img src="https://img.shields.io/badge/AWS-232F3E?style=stylefor-the-badge&logo=Amazon AWS&logoColor=FAFAFA"/> <img src="https://img.shields.io/badge/Lambda-FF9900?style=stylefor-the-badge&logo=AWS Lambda&logoColor=FAFAFA"/>
<img src="https://img.shields.io/badge/SQS-FF4F8B?style=stylefor-the-badge&logo=Amazon SQS&logoColor=FAFAFA"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=stylefor-the-badge&logo=JavaScript&logoColor=000000"/>
<img src="https://img.shields.io/badge/Express-000000?style=stylefor-the-badge&logo=Express&logoColor=FAFAFA"/>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=stylefor-the-badge&logo=MySQL&logoColor=FAFAFA"/>
<img src="https://img.shields.io/badge/Serverless-FD5750?style=stylefor-the-badge&logo=Serverless&logoColor=FAFAFA"/>
<img src="https://img.shields.io/badge/Postman-FF6C37?style=stylefor-the-badge&logo=Postman&logoColor=FAFAFA"/>
