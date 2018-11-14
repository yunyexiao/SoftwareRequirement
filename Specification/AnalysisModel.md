# 汉风堂外卖订餐系统

---

分析模型文档

V1.0

|更新日期|更新负责人|更新内容|版本|
|---|---|---|---|
|2018-11-14|恽叶霄|初步完成分析模型文档|V1.0|

---


## 1. 全局概念类图

![全局概念类图](models/全局.cd.png)


## 2. 全局用例图

![全局用例图](models/全局.uc.png)

## 3. 全局活动图

![全局活动图](models/全局.act.png)

## 4. CRC卡片

### 4.1 订餐平台

![订餐平台.crc](models/订餐平台.crc.png)

### 4.2 总经理平台

![总经理平台.crc](models/总经理平台.crc.png)

### 4.3 送餐员平台

![送餐员平台.crc](models/送餐员平台.crc.png)


## 5. 详细描述

### 5.1 用例1：查看菜单与菜品

#### 5.1.1 活动图

![uc1.act](models/用例1.act.png)

#### 5.1.2 顺序图

![uc1.sd](models/用例1.sd.png)

#### 5.1.3 状态图

![uc1.stm](models/用例1.stm.png)

### 5.2 用例2：在线订餐与支付

#### 5.2.1 活动图

![uc2.act](models/用例2.act.png)

#### 5.2.2 顺序图

![uc2.sd](models/用例2.sd.png)

#### 5.2.3 状态图

![uc2.stm](models/用例2.stm.png)

### 5.3 用例3：评价菜品与送餐员

#### 5.3.1 活动图

![uc3.act](models/用例3.act.png)

#### 5.3.2 顺序图

![uc3.sd](models/用例3.sd.png)

#### 5.3.3 状态图

![uc3.stm](models/用例3.stm.png)

### 5.4 用例4：分享平台与菜品

#### 5.4.1 活动图

![uc4.act](models/用例4.act.png)

#### 5.4.2 顺序图

![uc4.sd](models/用例4.sd.png)

#### 5.4.3 状态图

![uc4.stm](models/用例4.stm.png)

### 5.5 用例5：菜品管理

#### 5.5.1 活动图

![uc5.act](models/用例5.act.png)

#### 5.5.2 顺序图

![uc5.sd](models/用例5.sd.png)

#### 5.5.3 状态图

![uc5.stm](models/用例5.stm.png)

### 5.6 用例6：订单管理

#### 5.6.1 活动图

![uc6.act](models/用例6.act.png)

#### 5.6.2 顺序图

![uc6.sd](models/用例6.sd.png)

#### 5.6.3 状态图

![uc6.stm](models/用例6.stm.png)

### 5.7 用例7：促销策略制定

#### 5.7.1 活动图

![uc7.act](models/用例7.act.png)

#### 5.7.2 顺序图

![uc7.sd](models/用例7.sd.png)

#### 5.7.3 状态图

![uc7.stm](models/用例7.stm.png)

### 5.8 用例8：统计数据查看

#### 5.8.1 活动图

![uc8.act](models/用例8.act.png)

#### 5.8.2 顺序图

![uc8.sd](models/用例8.sd.png)

#### 5.8.3 状态图

![uc8.stm](models/用例8.stm.png)

### 5.9 用例9：送餐员管理

#### 5.9.1 活动图

![uc9.act](models/用例9.act.png)

#### 5.9.2 顺序图

![uc9.sd](models/用例9.sd.png)

#### 5.9.3 状态图

![uc9.stm](models/用例9.stm.png)

### 5.10 用例10：应聘者管理

#### 5.10.1 活动图

![uc10.act](models/用例10.act.png)

#### 5.10.2 顺序图

![uc10.sd](models/用例10.sd.png)

#### 5.10.3 状态图

![uc10.stm](models/用例10.stm.png)

### 5.11 用例11：接单与派单

#### 5.11.1 活动图

![uc11.act](models/用例11.act.png)

#### 5.11.2 顺序图

![uc11.sd](models/用例11.sd.png)

#### 5.11.3 状态图

![uc11.stm](models/用例11.stm.png)

### 5.12 用例12：送餐数据查看

#### 5.12.1 活动图

![uc12.act](models/用例12.act.png)

#### 5.12.2 顺序图

![uc12.sd](models/用例12.sd.png)

#### 5.12.3 状态图

![uc12.stm](models/用例12.stm.png)

### 5.13 用例13：排行榜查看

#### 5.13.1 活动图

![uc13.act](models/用例13.act.png)

#### 5.13.2 顺序图

![uc13.sd](models/用例13.sd.png)

#### 5.13.3 状态图

![uc13.stm](models/用例13.stm.png)

### 5.14 用例14：基础信息管理

#### 5.14.1 活动图

![uc14.act](models/用例14.act.png)

#### 5.14.2 顺序图

![uc14.sd](models/用例14.sd.png)

#### 5.14.3 状态图

![uc14.stm](models/用例14.stm.png)

### 5.15 用例15：身份认证与应聘

#### 5.15.1 活动图

![uc15.act](models/用例15.act.png)

#### 5.15.2 顺序图

![uc15.sd](models/用例15.sd.png)

#### 5.15.3 状态图

![uc15.stm](models/用例15.stm.png)

## 6. 操作契约

### 6.1 顾客平台
Context Customer::orderDish(dish: Dish):

  	Pre: self.isLoggedIn = true
  	
  	Post: self.order->count = self.order->count@pre + 1
	
Context Customer::pay():

  	Pre: self.isLoggedIn = true and order->count > 0
  	
  	Post: order->state = waitingForPaying

	
Context Customer::finishPay():

  	Pre: self.isLoggedIn = true and self.hasAddress = true and 
	self.hasPayway = true and self.isPasswordValid = true
  	
  	Post: order->state = accepting and ordList->count = orderList->count@pre + 1


### 6.2 总经理平台
Context Manager::seeOrders(orders: Set(Order)):

	Pre: self.isLoggedIn = true and OrderList->count > 0
	
Context Manager::setSpecials(dishes: Dish):

	Pre: self.isLoggedIn = true

	Post: dishes->specialPrice > 0 and dishes->specialPrice < dishes->originPrice
	
Context Manager::seeStatistics():

	Pre: self.isLoggedIn = true and OrderList->count > 0

Context Manager::getDelivermanList(search: String): Sequence(Deliverman)

	Pre: Manager.isLoggedIn = true
	
	Post: DelivermanList-> count = List.count and DelivermanList = List

Context Manager::getDelivermanDetail(delivermanId: Integer): Deliverman

	Pre: Manager.isLoggedIn = true
	
	Post: DelivermanForm->deliverman = Deliverman

Context Manager::dismissDeliverman(delivermanId: Integer): 

	Pre: Manager.isLoggedIn = true
	
	Post: DelivermanList->count = DelivermanList->count@pre - 1
	
Context Manager::getApplicantList(search: String): Sequence(Applicant)

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantList-> count = List.count and ApplicantList = List

Context Manager::getApplicantDetail(applicantId: Integer): Applicant

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantForm->applicant = Applicant

Context Manager::approveApplicant(applicantId: Integer):

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantList->select(a|a.id=applicantId)->forAll(a|a.approved=true)
	
Context Manager::ignoreApplicant(applicantId: Integer):

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantList->count=ApplicantList->count@pre-1


### 6.3 送餐员平台
Context Deliverman::getMeal(order: Order):

	Pre: self.isLoggedIn = true and order.deliverman = self

	Post: order.state = deliverying

Context Deliverman::finish(order: Order):

	Pre: self.isLoggedIn = true and order.deliverman = self

	Post: order.state = finished and 
	self.deliveryingList->count = self.deliveryingList->count@pre - 1 and 
	self.todayOrders->count = self.todayOrders->count@pre - 1 and 
	self.monthlyOrders->count = self.monthlyOrders->count@pre - 1

Context Deliverman::chooseOrders(orders: Set(Order)): boolean

	Pre: self.isLoggedIn = true and NewestOrderList->count > 0


### 6.4 应聘平台
Context Applicant::submitBasicForm(basicInfo: Form):
	
	Post: Applicant.verifyBasicInfo = true and system.camera.turnOn = true
	
Context Applicant::submitPhoto(faceImg: Pixels):
	
	Pre: Applicant.verifyBasicInfo = true 
	
	Post: Applicant.verifyFace = true and system.camera.turnOn = false
	
Context Applicant::verifyInfo():
	
	Pre: Applicant.verifyBasicInfo = true and Applicant.verifyFace = true
	
	Post: Applicant.approved = false

