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

