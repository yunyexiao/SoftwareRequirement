# 操作契约
## 顾客平台
Context Customer::orderDish(dish: Dish): void

  	Pre: self.isLoggedIn = true
  	
  	Post: self.order->count = self.order->count@pre + 1
	
Context Customer::pay(): void

  	Pre: self.isLoggedIn = true and order->count > 0
  	
  	Post: order->state = waitingForPaying

	
Context Customer::finishPay(): void

  	Pre: self.isLoggedIn = true and self.hasAddress = true and self.hasPayway = true and self.isPasswordValid = true
  	
  	Post: order->state = accepting and ordList->count = orderList->count@pre + 1


## 送餐员平台
Context Deliverman::getMeal(order: Order): void

	Pre: self.isLoggedIn = true and order.deliverman = self

	Post: order.state = deliverying

Context Deliverman::finish(order: Order): void

	Pre: self.isLoggedIn = true and order.deliverman = self

	Post: order.state = finished and self.deliveryingList->count = self
	.deliveryingList->count@pre - 1 and self.todayOrders->count = self
	.todayOrders->count@pre - 1 and self.monthlyOrders->count = self
	.monthlyOrders->count@pre - 1

Context Deliverman::chooseOrders(orders: Set(Order)): boolean

	Pre: self.isLoggedIn = true and NewestOrderList->count > 0


## 总经理平台
Context Manager::seeOrders(orders: Set(Order)): void

	Pre: self.isLoggedIn = true and OrderList->count > 0
	
Context Manager::setSpecials(dishes: Dish): void

	Pre: self.isLoggedIn = true
	Post: dishes->specialPrice > 0 and dishes->specialPrice < dishes->originPrice
	
Context Manager::seeStatistics(): void

	Pre: self.isLoggedIn = true and OrderList->count > 0


## 送餐员管理平台
Context Manager::getDelivermanList(search: String): List

	Pre: Manager.isLoggedIn = true
	
	Post: DelivermanList-> count = List.count and DelivermanList = List

Context Manager::getDelivermanDetail(delivermanId: Integer): Deliverman

	Pre: Manager.isLoggedIn = true
	
	Post: DelivermanForm->deliverman = Deliverman

Context Manager::dismissDeliverman(delivermanId: Integer): DatabaseResponse

	Pre: Manager.isLoggedIn = true
	
	Post: DelivermanList-> count --
	
  
## 应聘者管理平台
Context Manager::getApplicantList(search: String): List

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantList-> count = List.count and ApplicantList = List

Context Manager::getApplicantDetail(applicantId: Integer): Applicant

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantForm->applicant = Applicant

Context Manager::approveApplicant(applicantId: Integer): DatabaseResponse

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantList.select(applicantId).approved = true
	
Context Manager::ignoreApplicant(applicantId: Integer): DatabaseResponse

	Pre: Manager.isLoggedIn = true
	
	Post: ApplicantList-> count --


## 应聘平台
Context Applicant::submitBasicForm(basicInfo: Form): VerifyingResponse
	
	Post: Applicant.verifyBasicInfo = true and system.camera.turnOn = true
	
Context Applicant::submitPhoto(faceImg: Pixels): VerifyingResponse
	
	Pre: Applicant.verifyBasicInfo = true 
	
	Post: Applicant.verifyFace = true and system.camera.turnOn = false
	
Context Applicant::verifyInfo(): VerifyingResponse
	
	Pre: Applicant.verifyBasicInfo = true and Applicant.verifyFace = true
	
	Post: Applicant.approved = false and Database->save(Applicant.info)

