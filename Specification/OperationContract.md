# 操作契约

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

