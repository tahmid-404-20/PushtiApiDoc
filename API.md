# <div align="center">PUSHTI API Documentation</div>

### <div align="center"> Group 1 (A1) </div>

<div align="center">1. 1905002 - Nafis Tahmid </div>
<div align="center">2. 1905008 - Shattik Islam Rhythm </div>
<div align="center">3. 1905026 - Wasif Hamid </div>

----------------------------------------------

## Login

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
<br>

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
<br>

## Register

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
---------------
<br>

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
-------------
<br>

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
-----------------
<br>

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
---------------------
<br>

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
-----------------
<br>

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
------------------
<br>

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
<br>
