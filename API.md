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
>#### Request Body
>```json
>{
>
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "accountTypes": ["string"]
>}
>```
------------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/login/validate]()       |   `POST`     |

>### Request
>#### Request Body
>```json
>{
>    "accountType": "string",
>    "id": 123,
>    "password": "string"
>}
>```
<br>

>### Response - Success 
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "success": true,
>    "redirectURL": "string",
>    "token": "string"
>}
>```
<br>

> [!NOTE]
> Subsequent requests while logged in must contain this token.
<br>

>### Response - Wrong ID or Password
>#### Response Code: 401 (`Unauthorized`)
>
>#### Response Body
>```json
>{
>    "success": false,
>    "error": "Invalid ID or password"
>}
>```
-------------
<br>

## Register

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register]()                |   `GET`     |

>### Request
>#### Request Body
>```json
>{
>
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "redirectURL": "/register/farmer"
>}
>```
---------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/farmer]()                |   `GET`     |

>### Request
>#### Request Body
>```json
>{
>
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "farmerTypes": ["string"],
>    "divisions": ["string"]
>}
>```
-------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/sme]()                |   `GET`     |
| [/register/vendor]()       |    `GET`    |

>### Request
>#### Request Body
>```json
>{
>
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "divisions": ["string"]
>}
>```
-----------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/division]()                |   `POST`     |

>### Request
>#### Request Body
>```json
>{
>    "division": "string"
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "districts": ["string"]
>}
>```
---------------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/district]()                |   `POST`     |

>### Request
>#### Request Body
>```json
>{
>    "district": "string"
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "upazillas": ["string"]
>}
>```
-----------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/upazilla]()                |   `POST`     |

>### Request
>#### Request Body
>```json
>{
>    "upazilla": "string"
>}
>```
<br>

>### Response
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "unions": ["string"]
>}
>```
------------------
<br>

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/submit]()                |   `POST`     |

>### Request
>#### Request Body
>```json
>{
>    "accountType": "string",
>    "farmerType": "string",
>    "nid": 1234567890,
>    "name": "string",
>    "dob": "02-02-2000",
>    "address": "string",
>    "mobile": 123456789
>}
>```
<br>


>### Response - Success 
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>```json
>{
>    "success": true,
>    "redirectURL": "string",
>    "token": "string"
>}
>```
<br>

>### Response - Invalid Input
>#### Response Code: 422 (`Unprocessable Entity`)
>
>#### Response Body
>```json
>{
>    "success": false,
>    "error": "Invalid {field}"
>}
>```
-----------
<br>