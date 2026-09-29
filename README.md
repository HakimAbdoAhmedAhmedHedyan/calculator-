#Golden Grocer: Sales & Inventory Management System
#​بقالتك الذهبية نظام إدارة المبيعات والمنتجات
shop={}#القاموس
def add_product(): #دالة اضافة منتج 
    while True: #حلقة تكرار لاضافة المنتجات 
        back=input('\n  type "back" to return ') # ااذا اردت تتوقف الحلقه 
        if name == 'back': 
            break
        name=input ('enter  product name ')  #اادخل اسم المنتج
        price=int(input('enter product price ')) #ادخل السعر للمنتج
        quantity=int(input('enter product quantity ')) #ادخل الكمية 
    if name in shop: 
        shop[name]['quantity'] += quantity # If the product already exists, update its data. #    التاكد اذا المنتج موجود بالمحل
        shop[name]['price'] = price # Update the price if it changes. #التأكد من الكمية 
        print(f"Quantity updated! The current quantity of {name} is {shop[name]['quantity'] } ")#
    else:      # Add a new product
        shop[name]={"price":price,"quantity":quantity} 
        print(f'Added {name} successfully ')


def sell_product(): 
        name=input ('enter the name of the sold product: ')
        if name in shop: 
            quantity_to_sell=int(input('enter the quantity of sold product:  '))
            if quantity_to_sell<=shop[name]['quantity ']:  
                shop[name]['quantity'] -= quantity_to_sell 
                total =quantity_to_sell * shop[name]['price'] 
                print (f"Sale successful! Total price: {total}")
                print (f"The remaining quantity of {name}: {shop[name]['quantity']} ")
            else: 
                print(f"Insufficient quantity! Only available: {shop[name]['quantity']}")
        else: 
            print(f'this product is not available in the grocery store.')


def show_shop(): 
         print('\n---List of products in the grocery store--')
         if len(shop)==0:
             print('The grocery store is currently empty ')
         else: 
             for name, details in shop.items(): 
                 print(f"the product {name}| the price {details['price']}| Available quantity {details['quantity']}")
         print('------------')

while True: 
        print('\n{✅}Grocery Store Management System{💫} ')    
        print('1: Add a product ')
        print('2: Sell a product ')
        print('3: Display all product ')
        print('4: Exit ') 
        choose = input('choose the operation numer (1 to 4) ')
        if choose=='1': 
            add_product()
        elif choose=='2': 
            sell_product()
        elif choose =='3': 
            show_shop()
        elif choose =='4': 
           print('Exited the program. Thank you{😘} ')   
           break
        else:  
            print('Invalid option, please try again{😉}')    
                       
