# Agent

## Agent Module

### Dashboard

| API Endpoint         | HTTP Method |
| -------------------- | :---------: |
| [/agent/dashboard]() |    `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
> 
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
>   ```json
>   {
>       "name": "John Doe",
>       "email_id": "doe@gmail.com",
>       "avatar": "avatar23.png",
>       "Union": "Lorem",
>       "registration_stat": {
>           "no_farmers": 22,
>           "no_sme": 100,
>           "no_vendors": 50,
>       },
>       "treasery_status" : {
>           "loan_amount_farmer": 20,
>           "loan_amount_sme": 10,
>           "available": 70,
>       },
>       "transaction_stats": {
>           "total_loan": 250000,
>           "total_buy": 50000,
>           "total_sell": 100000,
>           "total_tax": 10000,
>       },
>       "tax_history_one_year": [
>           {
>               "month": "January",
>               "amount": 10000,
>           },
>           {
>               "month": "February",
>               "amount": 15000,
>           },
>           {
>               "month": "March",
>               "amount": 20000,
>           },
>           {
>               "month": "April",
>               "amount": 25000,
>           },
>           {
>               "month": "December",
>               "amount": 25000,
>           }
>       ],  
> }
> ```

</br>

---

## Loan Module
### Loan-Requests 

| API Endpoint     | HTTP Method |
| ---------------- | :---------: |
| [/agent/loan]() |    `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>    
> }
> ```
>

> </br>

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>    "request_farmers": [
>        {  
>        "request_id": 2441139,
>        "name": "John Doe",
>        "avatar_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
>        "type": "Dairy",
>        "rank": "Gold",
>        "point": 4804,
>        "loan_amount_min": 2000,
>        "loan_amount_max": 5000,
>        "description": "I need money for my farm",
>        "status": "stage1"
>         },
>        {  
>        "request_id": 2441140,
>        "name": "John Mike",
>        "avatar_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
>        "type": "Dairy",
>        "rank": "Gold",
>        "point": 4804,
>        "loan_amount_min": 2000,
>        "loan_amount_max": 5000,
>        "description": "I need money for my farm",
>        "status": "stage2"
>         }         
>      ],
>
>    "request_smes": [
>        {  
>        "request_id": 8441183,
>        "name": "John Doe",
>        "avatar_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
>        "type": "Dairy",
>        "rank": "Gold",
>        "point": 4804,
>        "loan_amount_min": 2000,
>        "loan_amount_max": 5000,
>        "description": "I need money for my farm",
>        "status": "stage1"
>         },
>        {  
>        "request_id": 8441140,
>        "name": "John Mike",
>        "avatar_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
>        "type": "Dairy",
>        "rank": "Gold",
>        "point": 4804,
>        "loan_amount_min": 2000,
>        "loan_amount_max": 5000,
>        "description": "I need money for my farm",
>        "status": "stage2"
>         }         
>   ],
> }
> ```
>

</br>

---

### Respond to Loan Request

#### For next stage

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/loan/response]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "request_id": 2441140,
>   "next": true,
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Moved to next stage successfully"
> }
> ```

</br>

> ### Response - Failure
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Failed to move to next stage"
> }
> ```

#### For acceptance (Final Stage)

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/loan/accept]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "request_id": 2441140,
>   "accepted" : true,
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Loan Accepted Successfully"
> }
> ```

</br>

> ### Response - Failure
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Loan Acceptance Failed"
> }
> ```

</br>

---

## Transaction Module

### Transaction History

#### For Farmers

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/farmer]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>       "buy_history": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "John Doe",
>               "avatar": "avatar23.png",
>               "total": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Done"
>           },
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "John Doe",
>               "avatar": "avatar44.png",
>               "total": 10023,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>       ],
> }
> ```

#### For Vendors

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/vendor]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>       "sell_history": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "John Doe",
>               "avatar": "avatar23.png",
>               "total": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Done"
>           },
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "John Doe",
>               "avatar": "avatar44.png",
>               "total": 10023,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>       ],
> }
> ```


#### For SMEs

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>       "sell_history": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "sme": "Dolores Sitamet",
>               "avatar": "avatar23.png",
>               "total": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Done"
>           },
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "Lorem Ipsum",
>               "avatar": "avatar44.png",
>               "total": 10023,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>        ],
>
>       "buy_history": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "Doe",
>               "avatar": "avatar23.png",
>               "total": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Done"
>           },
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "farmer": "John",
>               "avatar": "avatar44.png",
>               "total": 10023,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   },
>                   {
>                       "name": "Sitamet",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>       ],
> }
> ```

### New Transaction

#### For Farmers

#### Initiating buy request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/farmer/buy]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "farmers": [
>       {
>           "farmer_id" : 12345667,
>           "name": "Lorem Ipsum",
>           "avatar": "avatar23.png",
>           "type": "Dairy",
>           "address": "Lorem Sitame",
>        },
>       {
>           "farmer_id" : 12345669,
>           "name": "Loremis Opiumis",
>           "avatar": "avatar23.png",
>           "type": "Dairy",
>           "address": "Lorem ame",
>        },
>       ],
>   "products": [
>       {
>           "id" : 23,
>           "name": "Milk",
>           "unit_price": 100,
>        },
>       {
>           "id" : 24,
>           "name": "Beef",
>           "unit_price": 500,
>        },
>  ],
> }
> ```


#### Adding new products to buy request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/farmer/buy/add]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "farmer_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "deduction_amount": 1000,
>   "tax_amount": 100,
> }
> ```

</br>

> ### Response - Budget Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough budget available"
> }
> ```

</br>


#### Buy request to farmer

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/farmer/buy/request]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "farmer_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Request sent successfully"
> }
> ```

</br>

> ### Response - Budget Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough budget available"
> }
> ```

</br>


### For Vendors

#### Initiating sell request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/vendor/sell]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "vendors": [
>       {
>           "vendor_id" : 12345667,
>           "name": "Lorem Ipsum",
>           "avatar": "avatar23.png",
>           "address": "Lorem Sitame",
>        },
>       {
>           "vendor_id" : 12345669,
>           "name": "Loremis Opiumis",
>           "avatar": "avatar23.png",
>           "address": "Lorem ame",
>        },
>       ],
>   "products": [
>       {
>           "id" : 23,
>           "name": "Milk",
>           "unit_price": 100,
>        },
>        {
>           "id" : 24,
>           "name": "Butter",
>           "unit_price": 500,
>        },
>  ],
> }
> ```


#### Adding new products to sell request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/vendor/sell/add]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "vendor_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "discount_amount": 1500,
>   "tax_amount": 100,
> }
> ```

</br>

> ### Response - Inventory Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough inventory available"
> }
> ```

</br>


#### Sell request to vendor

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/vendor/sell/request]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "vendor_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Request sent successfully"
> }
> ```

</br>

> ### Response - Inventory Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough inventory available"
> }
> ```

</br>

### For SMEs

#### Initiating buy request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme/buy]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "smes": [
>       {
>           "sme_id" : 12345667,
>           "name": "Lorem Ipsum",
>           "avatar": "avatar23.png",
>           "type": "Dairy",
>           "address": "Lorem Sitame",
>        },
>       {
>           "sme_id" : 12345669,
>           "name": "Loremis Opiumis",
>           "avatar": "avatar23.png",
>           "type": "Dairy",
>           "address": "Lorem ame",
>        },
>       ],
>   "products": [
>       {
>           "id" : 23,
>           "name": "Milk",
>           "unit_price": 100,
>        },
>       {
>           "id" : 24,
>           "name": "Beef",
>           "unit_price": 500,
>        },
>  ],
> }
> ```


#### Adding new products to buy request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme/buy/add]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "sme_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "deduction_amount": 1000,
>   "tax_amount": 100,
> }
> ```

</br>

> ### Response - Budget Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough budget available"
> }
> ```

</br>


#### Buy request to sme

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme/buy/request]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "sme_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Request sent successfully"
> }
> ```

</br>

> ### Response - Budget Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough budget available"
> }
> ```

</br>


### For Vendors

#### Initiating sell request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme/sell]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

> ### Response
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "smes": [
>       {
>           "sme_id" : 12345667,
>           "name": "Lorem Ipsum",
>           "avatar": "avatar23.png",
>           "address": "Lorem Sitame",
>        },
>       {
>           "sme_id" : 12345669,
>           "name": "Loremis Opiumis",
>           "avatar": "avatar23.png",
>           "address": "Lorem ame",
>        },
>       ],
>   "products": [
>       {
>           "id" : 23,
>           "name": "Milk",
>           "unit_price": 100,
>        },
>        {
>           "id" : 24,
>           "name": "Butter",
>           "unit_price": 500,
>        },
>  ],
> }
> ```


#### Adding new products to sell request

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme/sell/add]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "sme_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "discount_amount": 1500,
>   "tax_amount": 100,
> }
> ```

</br>

> ### Response - Inventory Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough inventory available"
> }
> ```

</br>


#### Sell request to sme

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/transaction/sme/sell/request]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "sme_id": 123456789,
>   "products": [
>       {  
>           "product_id": 23,
>           "name": "Milk",  
>           "quantity": 10,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>       },
>   ],
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Request sent successfully"
> }
> ```

</br>

> ### Response - Inventory Error
>
> #### Response Code : 400 (`Bad Request`)
>
> #### Response Body
>
> ```json
> {
>   "success": false,
>   "message": "Not enough inventory available"
> }
> ```

</br>