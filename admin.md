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
>    "messages": [{
>                   "id": 123,
>                   "name": "Mofiz Mia",
>                   "union": "Vandaria",
>                   "rank": "Gold",
>                   "points": 321,
>                   "accountType": "Farmer",
>                   "farmerType": "Dairy",
>                   "subject": "Loan is not approved.",
>                   "details": "I have waited for a long time. Agent is not approving or rejecting my loan request."                      
>                }]
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
| [/admin/profile/loan]()                |   `GET`     |

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
