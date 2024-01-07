# <div align="center">PUSHTI API Documentation</div>

### <div align="center"> Group 1 (A1) </div>

<div align="center">1. 1905002 - Nafis Tahmid </div>
<div align="center">2. 1905008 - Shattik Islam Rhythm </div>
<div align="center">3. 1905026 - Wasif Hamid </div>

----------------------------------------------

## Index

1. [Register/ Login Module](#register/login-module)
    1. [Login](#login)
    2. [Login Validation](#login-validate)
    3. [Register](#register)
        - [Get Division List and Type List for Farmers](#get-division-list-and-type-list-for-farmers)
        - [Get Division List for SME/Vendors](#get-division-list-for-smevendors)
        - [Get District List For Divisions](#get-district-list-for-divisions)
        - [Get Upazilla List For District](#get-upazilla-list-for-district)
        - [Get Union List For Upazilla](#get-union-list-for-upazilla)
    4. [Submit Registration Request](https://github.com/Shattik/PushtiApiDoc/blob/master/Combined.MD#submit-registration-request)
2. []

## Register/Login Module

### Login

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/login]()                |   `GET`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "accountTypes": [
>                       "Admin",
>                       "Agent",
>                       "Farmer",
>                       "SME",
>                       "Vendor"
>                    ]
>}
>```
>
------------------

### Login Validate

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/login/validate]()       |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "accountType": "Farmer",
>    "id": 123,
>    "password": "abcd"
>}
>```
>
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "success": true,
>    "redirectURL": "farmer/dashboard",
>    "token": "123abc123"
>}
>```
>
<br>

> [!NOTE]
> Subsequent requests while logged in must contain this token.
<br>

>### Response - Wrong ID or Password
>
>#### Response Code: 401 (`Unauthorized`)
>
>#### Response Body
>
>```json
>{
>    "success": false,
>    "error": "Invalid ID or password"
>}
>```
>
-------------

### Register

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register]()                |   `GET`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "redirectURL": "/register/farmer"
>}
>```
>

#### Get Division List and Type List for Farmers

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/farmer]()                |   `GET`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "farmerTypes": [
>                        "Dairy", 
>                        "Poultry"
>                   ],
>    "divisions": [
>                        "Dhaka", 
>                        "Sylhet"
>                 ]
>}
>```
>

#### Get Division List for SME/Vendors

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/sme]()                |   `GET`     |
| [/register/vendor]()       |    `GET`    |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "divisions": [
>                        "Dhaka",
>                        "Sylhet"
>                 ]
>}
>```
>

#### Get District List For Divisions

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/division]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "division": "Sylhet"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "districts": [
>                        "Sylhet",
>                        "Moulvibazar"
>                 ]
>}
>```
>

#### Get Upazilla List for District

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/district]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "district": "Moulvibazar"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "upazillas": [
>                        "Lalganj"
>                        "Sreemangal"
>                 ]
>}
>```
>

#### Get Union List for Upazilla

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/upazilla]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "upazilla": "Lalganj"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "unions": [
>                    "Haatimara",
>                    "Chanpur"
>              ]
>}
>```
>

---

### Submit Registration Request

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/submit]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "accountType": "Vendor",
>    "farmerType": null,
>    "nid": 1234567890,
>    "name": "Lal Mia",
>    "dob": "02-02-2000",
>    "address": "Nilpur, Borodighi, Moulvibazar",
>    "mobile": 123456789
>}
>```
>
<br>

> [!NOTE]
> Farmer type will be null for SME or vendor accounts and will be ignored by the backend.
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "success": true,
>    "redirectURL": "vendor/dashboard",
>    "token": "1234cdb32"
>}
>```
>
<br>

>### Response - Invalid Input
>
>#### Response Code: 422 (`Unprocessable Entity`)
>
>#### Response Body
>
>```json
>{
>    "success": false,
>    "error": "Invalid {field}"
>}
>```
>

-----------

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

---

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

</br>

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

---

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


#### For Vendors

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
>           "quantity": 10,
>        },
>        {
>           "id" : 24,
>           "name": "Butter",
>           "unit_price": 500,
>           "quantity": 10,
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


#### For SMEs

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
>        {
>           "id" : 24,
>           "name": "Butter",
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
>           "quantity": 10,
>        },
>        {
>           "id" : 24,
>           "name": "Butter",
>           "unit_price": 500,
>           "quantity": 10,
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

---

### Inventory

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/inventory]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
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
>   "products": [
>       {
>           "name": "Milk",
>           "quantity": 10,
>           "unit_price": 100,
>       },
>       {
>           "name": "Rosogolla",
>           "quantity": 10,
>           "unit_price": 220,
>       },
>       {
>           "name": "Butter",
>           "quantity": 10,
>           "unit_price": 400,
>       },
>   ],
> }
> ```

---

### Leaderboard

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/leaderboard]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
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
>   "farmer_leaderboard": [
>       {   
>           "rank": 1,
>           "name": "Lorem",
>           "avatar": "avatar23.png",
>           "points": 2345,
>       },
>       {   
>           "rank": 2,
>           "name": "Dorles",
>           "avatar": "avatar23.png",
>           "points": 2344,
>       },
>   ],
>
>   "sme_leaderboard": [
>       {   
>           "rank": 1,
>           "name": "Loremq",
>           "avatar": "avatar23.png",
>           "points": 2345,
>       },
>       {   
>           "rank": 2,
>           "name": "Dorlesi",
>           "avatar": "avatar23.png",
>           "points": 2344,
>       },
>   ],
>
>   "vendor_leaderboard": [
>       {   
>           "rank": 1,
>           "name": "Lorema",
>           "avatar": "avatar23.png",
>           "points": 2345,
>       },
>       {   
>           "rank": 2,
>           "name": "Dorlesa",
>           "avatar": "avatar23.png",
>           "points": 2344,
>       },
>   ],
>
>   "union_leaderboard": [
>       {   
>           "rank": 1,
>           "name": "Asmodios",
>           "upazilla": "Lalpur",
>           "avatar": "avatar23.png",
>           "points": 2345012,
>       },
>       {   
>           "rank": 2,
>           "name": "Lucifer",
>           "upazilla": "Bucharest",
>           "avatar": "avatar23.png",
>           "points": 2344010,
>       },
>   ],
> }
> ```

---

### Support

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/support]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
> }
> ```

</br>

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
>    ```json
>    "previous tickets": [
>       {
>           "ticketId": 123456789,
>           "date": "2022-10-31T11:00:00Z",
>           "status": "Pending",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       },
>       {
>           "ticketId": 123456789,
>          "date": "2022-10-31T09:00:00Z",
>           "status": "Resolved",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       }
>   ]
>   ```

---

### New Ticket


| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/agent/support/send]() |   `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "subject": "Lorem Ipsum",
>   "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incid idunt utlabore et dolore magna aliqua. Vel quam elementum pulvinar etiam. At auctor urna nunc id cursus metus aliquam",
> }
> ```

> ### Response - Success
>
> #### Response Code : 200 (`OK`)
>
> #### Response Body
>
> ```json
> {
>   "success": true,
>   "message": "Ticket sent successfully"
> }
> ```

---

## Farmer Module

### Dashboard

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/dashboard]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "name": "John Doe",
>       "nid": 123456789,
>       "Agent": "Dolores Sitamet",
>       "avatar": "img-src.png",
>       "Union": "Lorem",
>       "Status": {
>           "rank": "Gold",
>           "points": 100,
>           "points to next level": 50,
>           "benifits": [
>               "5% Extra Tax Deduction",
>               "2.5% VAT taken (half of the usual)",
>           ]    
>       },
>       "sell history": [
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
>   }
>    ```

---

### Loan

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/loan]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```
>
</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "active loan":  {
>           "start date": "2022-10-31T11:00:00Z",    
>           "amount": 10000,
>           "remaining": 5000,
>           "interest": 10,
>           "status": "active",
>       },
>       "loan history": [
>           {
>               "start date": "2022-10-31T11:00:00Z",
>               "end date": "2022-10-31T11:00:00Z",
>               "amount": 10000,
>               "status": "completed"
>           },
>           {
>               "start date": "2022-10-31T11:00:00Z",
>               "end date": "2022-10-31T11:00:00Z",
>               "amount": 15000,
>               "status": "rejected"
>           }
>       ]
>   }
>    ```

---

### Loan Request

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/loan/request]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "max amount": 10000,
>       "min amount": 5000,
>       "description": "I need money for my farm",
>   }
>    ```

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "success": true,
>       "message": "Loan Requested Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>       "success": false,
>       "message": "Loan Request Failed"
>   }
>    ```

---

### Sell History

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/sell]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```
>

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "Sell History": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Meat",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ],
>       "Pending Requests": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Calf",
>                       "quantity": 1,
>                       "price": 1000
>                   }
>               ],
>           }
>       ]
>   }
>    ```
>

---

### Sell Response

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/sell/response]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "tid": 123456789,
>       "status": "Accepted"
>   }
>    ```

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Response Sent Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Response Failed"
>   }
>    ```

---

### Leaderboard

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/leaderboard]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
> 
>    }
>    ```

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   [
>       {
>           "name": "John Doe",
>           "rank": 1,
>           "points":12355,
>           "avatar": "img-src.png"
>       },
>      {
>           "name": "Candice Wu",
>           "rank": 2,
>           "points":12155,
>           "avatar": "img-src.png"
>       },
>      {
>           "name": "Dolores Sitamet",
>           "rank": 3,
>           "points":12055,
>           "avatar": "img-src.png"
>       }
>   ]
>   ```

---

### Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/support]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>    "previous tickets": [
>       {
>           "ticketId": 123456789,
>           "date": "2022-10-31T11:00:00Z",
>           "status": "Pending",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       },
>       {
>           "ticketId": 123456789,
>          "date": "2022-10-31T09:00:00Z",
>           "status": "Resolved",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       }
>   ]
>   ```

---

### Send Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/farmer/support/send]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "subject": "Buy Request Cancelled",
>       "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>   }

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Ticket Created Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Ticket Creation Failed"
>   }
>    ```

--

## SME Module

### Dashboard

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/dashboard]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "name": "John Doe",
>       "nid": 123456789,
>       "Agent": "Dolores Sitamet",
>       "avatar": "img-src.png",
>       "Union": "Lorem",
>       "Status": {
>           "rank": "Gold",
>           "points": 100,
>           "points to next level": 50,
>           "benifits": [
>               "5% Less Tax Deduction",
>               "2.5% VAT taken (half of the usual)",
>           ]    
>       },
>       "sell history": [
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
>       "buy history": [
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
>   }
>    ```

---

### Loan

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/loan]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```
>
</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "active loan":  {
>           "start date": "2022-10-31T11:00:00Z",    
>           "amount": 10000,
>           "remaining": 5000,
>           "interest": 10,
>           "status": "active",
>       },
>       "loan history": [
>           {
>               "start date": "2022-10-31T11:00:00Z",
>               "end date": "2022-10-31T11:00:00Z",
>               "amount": 10000,
>               "status": "completed"
>           },
>           {
>               "start date": "2022-10-31T11:00:00Z",
>               "end date": "2022-10-31T11:00:00Z",
>               "amount": 15000,
>               "status": "rejected"
>           }
>       ]
>   }
>    ```

---

### Loan Request

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/loan/request]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "max amount": 10000,
>       "min amount": 5000,
>       "description": "I need money for my farm",
>   }
>    ```

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "success": true,
>       "message": "Loan Requested Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>       "success": false,
>       "message": "Loan Request Failed"
>   }
>    ```

---

### Buy History

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/buy]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```
>

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "Buy History": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ],
>       "Pending Requests": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>           }
>       ]
>   }
>    ```
>

---

### Buy Response

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/buy/response]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "tid": 123456789,
>       "status": "Accepted"
>   }
>    ```

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Response Sent Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Response Failed"
>   }
>    ```

---

### Sell History

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/sell]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```
>

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "Sell History": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Curd",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Ghee",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ],
>       "Pending Requests": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Sweets",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Curd",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>           }
>       ]
>   }
>    ```
>

---

### Sell Response

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/sell/response]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "tid": 123456789,
>       "status": "Accepted"
>   }
>    ```

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Response Sent Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Response Failed"
>   }
>    ```

---

### Leaderboard

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/leaderboard]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
> 
>    }
>    ```

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   [
>       {
>           "name": "John Doe",
>           "rank": 1,
>           "points":12355,
>           "avatar": "img-src.png"
>       },
>      {
>           "name": "Candice Wu",
>           "rank": 2,
>           "points":12155,
>           "avatar": "img-src.png"
>       },
>      {
>           "name": "Dolores Sitamet",
>           "rank": 3,
>           "points":12055,
>           "avatar": "img-src.png"
>       }
>   ]
>   ```

---

### Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/support]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>    "previous tickets": [
>       {
>           "ticketId": 123456789,
>           "date": "2022-10-31T11:00:00Z",
>           "status": "Pending",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       },
>       {
>           "ticketId": 123456789,
>          "date": "2022-10-31T09:00:00Z",
>           "status": "Resolved",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       }
>   ]
>   ```

---

### Send Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/SME/support/send]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "subject": "Buy Request Cancelled",
>       "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>   }

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Ticket Created Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Ticket Creation Failed"
>   }
>    ```

---

### Inventory

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/SME/inventory]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
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
>   "products": [
>       {
>           "name": "Milk",
>           "quantity": 10,
>           "unit_price": 100,
>       },
>       {
>           "name": "Rosogolla",
>           "quantity": 10,
>           "unit_price": 220,
>       },
>       {
>           "name": "Butter",
>           "quantity": 10,
>           "unit_price": 400,
>       },
>   ],
> }
> ```

---

## Vendor Module

### Dashboard

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/vendor/dashboard]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "name": "John Doe",
>       "nid": 123456789,
>       "Agent": "Dolores Sitamet",
>       "avatar": "img-src.png",
>       "Union": "Lorem",
>       "Status": {
>           "rank": "Gold",
>           "points": 100,
>           "points to next level": 50,
>           "benifits": [
>               "5% Less Tax Deduction",
>               "2.5% VAT taken (half of the usual)",
>           ]    
>       },
>       "sell history": [
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
>       "buy history": [
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
>   }
>    ```

---

### Buy History

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/vendor/buy]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```
>

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "Buy History": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ],
>       "Pending Requests": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>           }
>       ]
>   }
>    ```
>

---

### Buy Response

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/vendor/buy/response]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "tid": 123456789,
>       "status": "Accepted"
>   }
>    ```

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Response Sent Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Response Failed"
>   }
>    ```

---

### Leaderboard

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/vendor/leaderboard]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
> 
>    }
>    ```

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   [
>       {
>           "name": "John Doe",
>           "rank": 1,
>           "points":12355,
>           "avatar": "img-src.png"
>       },
>      {
>           "name": "Candice Wu",
>           "rank": 2,
>           "points":12155,
>           "avatar": "img-src.png"
>       },
>      {
>           "name": "Dolores Sitamet",
>           "rank": 3,
>           "points":12055,
>           "avatar": "img-src.png"
>       }
>   ]
>   ```

---

### Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/vendor/support]() |   `GET`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>
>    }
>    ```

</br>

>### Response
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>    "previous tickets": [
>       {
>           "ticketId": 123456789,
>           "date": "2022-10-31T11:00:00Z",
>           "status": "Pending",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       },
>       {
>           "ticketId": 123456789,
>          "date": "2022-10-31T09:00:00Z",
>           "status": "Resolved",
>           "subject": "Buy Request Cancelled",
>           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>       }
>   ]
>   ```

---

### Send Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/vendor/support/send]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "subject": "Buy Request Cancelled",
>       "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo eiusmod tempor incididunt ut labore et dolore magna aliqua. Convallis tellus id interdum velit laoreet. Enim eu turpis egestas pretium. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor"
>   }

</br>

>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": true,
>      "message": "Ticket Created Successfully"
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 400 (`Bad Request`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "Ticket Creation Failed"
>   }
>    ```

---

### Inventory

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/vendor/inventory]() |   `GET`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>
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
>   "products": [
>       {
>           "name": "Milk",
>           "quantity": 10,
>           "unit_price": 100,
>       },
>       {
>           "name": "Rosogolla",
>           "quantity": 10,
>           "unit_price": 220,
>       },
>       {
>           "name": "Butter",
>           "quantity": 10,
>           "unit_price": 400,
>       },
>   ],
> }
> ```

---

## Admin Module

### Admin Support Mailbox

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/support]()                |   `GET`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "messages": [
>        {
>                   "id": 123,
>                   "ticket id": 1324,
>                   "name": "Mofiz Mia",
>                   "union": "Vandaria",
>                   "rank": "Gold",
>                   "points": 321,
>                   "accountType": "Farmer",
>                   "farmerType": "Dairy",
>                   "subject": "Loan is not approved.",
>                   "details": "I have waited for a long time. Agent is not approving or rejecting my loan request."                      
>        }
>   ]
>}
>```
>

-----------------

### Show User Profile to Admin

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/profile]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "id": 1234  
>}
>```
>
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "details": {
>                   "name": "Baten Mia",
>                    "accountType": "SME",
>                    "farmerType": null,
>                    "rank": "Platinum",
>                    "union": "Lalpur",
>                    "agentName": "Samsul Haq"
>               }
>}
>```
>
<br>

>### Response - Invalid ID
>
>#### Response Code: 404 (`Not Found`)
>
>```json
>{
>    "error": "Invalid ID"
>}
>```
>
-----------------

### Show Transaction History to Admin

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/profile/transaction]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "id": 1234  
>}
>```
>
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "Buy History": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>               "status": "Rejected"
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ],
>    "Pending Buy Requests": [
>           {
>               "tid": 123456789,    
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 1000,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 10,
>                       "price": 1000
>                   }
>               ],
>           },
>           {
>               "tid": 123456789,
>               "date": "2022-10-31T11:00:00Z",
>               "amount": 500,
>               "Objects": [
>                   {
>                       "name": "Milk",
>                       "quantity": 5,
>                       "price": 500
>                   }
>               ],
>           }
>       ],
>     "Sell History": null,
>     "Pending Sell Requests": null
>}
>```
>
<br>

> [!NOTE]
> Sell related fields will be null for vendors and buy related fields will be null for farmers.

<br>

>### Response - Invalid ID
>
>#### Response Code: 404 (`Not Found`)
>
>```json
>{
>    "error": "Invalid ID"
>}
>```
>
-----------------

### Show Loan History to Admin

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/profile/loan]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "id": 123
>}
>```
>
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "active loan":  {
>           "start date": "2022-10-31T11:00:00Z",    
>           "amount": 10000,
>           "remaining": 5000,
>           "interest": 10,
>           "status": "active",
>       },
>     "loan history": [
>           {
>               "start date": "2022-10-31T11:00:00Z",
>               "end date": "2022-10-31T11:00:00Z",
>               "amount": 10000,
>               "status": "completed"
>           },
>           {
>               "start date": "2022-10-31T11:00:00Z",
>               "end date": "2022-10-31T11:00:00Z",
>               "amount": 15000,
>               "status": "rejected"
>           }
>       ]
>}
>```
>

<br>

> [!NOTE]
> If there is no active loan, the field will be null. Both fields will be null for vendors.

<br>


>### Response - Invalid ID
>
>#### Response Code: 404 (`Not Found`)
>
>```json
>{
>    "error": "Invalid ID"
>}
>```
>
-----------------

### Show Products & Pricing

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/products]()                |   `GET`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "products": [
>       {
>           "productID": 3,
>           "name": "Milk",
>           "tax": 5,
>           "unit_price": 100,
>       },
>       {
>           "productID": 4,
>           "name": "Rosogolla",
>           "tax": 10,
>           "unit_price": 220,
>       },
>       {
>           "productID": 7,
>           "name": "Butter",
>           "tax": 5,
>           "unit_price": 400,
>       },
>   ],
>}
>```
>
-----------------

### Edit Price and Tax of product

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/products/edit]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "productID": 12,
>   "price": 410,
>   "tax": 7
>}
>```
>
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "success": true;
>}
>```
>
<br>

>### Response - Invalid ID
>
>#### Response Code: 404 (`Not Found`)
>
>```json
>{
>    "success": false,
>    "error": "Invalid product ID"
>}
>```
>
-----------------

### Report Generation

#### Get Division List

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/report]()                |   `GET`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "divisions": [
>                      "Dhaka",
>                      "Sylhet",
>                      "Khulna"  
>                 ]
>}
>```
>

#### Get Division Report and District List

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/report/division]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "division": "Khulna"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "districts": [
>                   "Khulna",
>                   "Bagerhat",
>                   "Madaripur",                     
>                 ],
>    "registration_stat": {
>           "no_farmers": 22000,
>           "no_sme": 10000,
>           "no_vendors": 50000,
>       },
>    "treasery_status" : {
>           "loan_amount_farmer": 20,
>           "loan_amount_sme": 10,
>           "available": 70,
>       },
>    "transaction_stats": {
>           "total_loan": 25000000,
>           "total_buy": 50000000,
>           "total_sell": 100000000,
>           "total_tax": 10000000,
>       },
>     "tax_history_one_year": [
>           {
>               "month": "January",
>               "amount": 10000000,
>           },
>           {
>               "month": "February",
>               "amount": 15000000,
>           },
>           {
>               "month": "March",
>               "amount": 20000000,
>           },
>           {
>               "month": "April",
>               "amount": 25000000,
>           },
>           {
>               "month": "December",
>               "amount": 2500000,
>           }
>       ],  
>}
>```
>

#### Get District Report and Upazilla List

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/report/district]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "district": "Bagerhat"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "upazillas": [
>                   "Pachgaon",
>                   "Haatpur",
>                   "Muradpur",                     
>                 ],
>    "registration_stat": {
>           "no_farmers": 2200,
>           "no_sme": 1000,
>           "no_vendors": 5000,
>       },
>    "treasery_status" : {
>           "loan_amount_farmer": 20,
>           "loan_amount_sme": 10,
>           "available": 70,
>       },
>    "transaction_stats": {
>           "total_loan": 250000,
>           "total_buy": 500000,
>           "total_sell": 1000000,
>           "total_tax": 100000,
>       },
>     "tax_history_one_year": [
>           {
>               "month": "January",
>               "amount": 100000,
>           },
>           {
>               "month": "February",
>               "amount": 150000,
>           },
>           {
>               "month": "March",
>               "amount": 200000,
>           },
>           {
>               "month": "April",
>               "amount": 250000,
>           },
>           {
>               "month": "December",
>               "amount": 25000,
>           }
>       ],  
>}
>```
>

#### Get Upazilla Report and Union List

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/report/upazilla]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "upazilla": "Muradpur"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "unions": [
>                   "Aluganj",
>                   "Belpukur",                     
>              ],
>    "registration_stat": {
>           "no_farmers": 2200,
>           "no_sme": 1000,
>           "no_vendors": 5000,
>       },
>    "treasery_status" : {
>           "loan_amount_farmer": 20,
>           "loan_amount_sme": 10,
>           "available": 70,
>       },
>    "transaction_stats": {
>           "total_loan": 250000,
>           "total_buy": 500000,
>           "total_sell": 100000,
>           "total_tax": 100000,
>       },
>     "tax_history_one_year": [
>           {
>               "month": "January",
>               "amount": 100000,
>           },
>           {
>               "month": "February",
>               "amount": 150000,
>           },
>           {
>               "month": "March",
>               "amount": 200000,
>           },
>           {
>               "month": "April",
>               "amount": 250000,
>           },
>           {
>               "month": "December",
>               "amount": 250000,
>           }
>       ],  
>}
>```
>

#### Get Union Report

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/report/union]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "union": "Belpukur"
>}
>```
>
<br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "agentName": "Kamrul Hasan",
>    "nid": 123456,
>    "phone": 0123445,
>    "email": "kamrul@gmail.com",
>    "registration_stat": {
>           "no_farmers": 220,
>           "no_sme": 100,
>           "no_vendors": 500,
>       },
>    "treasery_status" : {
>           "loan_amount_farmer": 20,
>           "loan_amount_sme": 10,
>           "available": 70,
>       },
>    "transaction_stats": {
>           "total_loan": 250000,
>           "total_buy": 500000,
>           "total_sell": 100000,
>           "total_tax": 10000,
>       },
>     "tax_history_one_year": [
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
>               "amount": 2000,
>           },
>           {
>               "month": "April",
>               "amount": 25000,
>           },
>           {
>               "month": "December",
>               "amount": 2500,
>           }
>       ],  
>}
>```
>
-----------------

### Change Union Agent

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/report/union/change]()                |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>   "id": 123,
>   "name": "Forid Khan",
>   "nid": 654321,
>   "phone": 321453,
>   "email": "khanforid@yahoo.com"
>}
>```
>
<br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "success": true,
>}
>```
>
<br>

>### Response - Invalid ID
>
>#### Response Code: 404 (`Not Found`)
>
>#### Response Body
>
>```json
>{
>   "success": false,
>   "error": "Invalid agent ID"    
>}
>```
