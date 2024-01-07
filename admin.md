## Admin

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
<br>

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
<br>

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
<br>

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
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/update]()                |   `GET`     |

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
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/admin/update/edit]()                |   `POST`     |

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
<br>

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
-----------------
<br>

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
-----------------
<br>

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
-----------------
<br>

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
-----------------
<br>

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
<br>

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
-----------------
<br>
