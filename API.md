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

#### Request Body
```json
{

}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "accountTypes": ["string"]
}
```
------------------

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/login/validate]()       |   `POST`     |

#### Request Body
```json
{
    "accountType": "string",
    "id": 123,
    "password": "string"
}
```
### Success 
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "success": true,
    "redirectURL": "string",
    "token": "string"
}
```
### Wrong ID or Password
Response Code: 401 (`Unauthorized`)

#### Response Body
```json
{
    "success": false,
    "error": "Invalid ID or password"
}
```
-------------

## Register

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register]()                |   `GET`     |

#### Request Body
```json
{

}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "redirectURL": "/register/farmer"
}
```
---------------

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/farmer]()                |   `GET`     |

#### Request Body
```json
{

}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "farmerTypes": ["string"],
    "divisions": ["string"]
}
```
-------------

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/sme]()                |   `GET`     |
| [/register/vendor]()       |    `GET`    |

#### Request Body
```json
{

}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "divisions": ["string"]
}
```
-----------------

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/division]()                |   `POST`     |

#### Request Body
```json
{
    "division": "string"
}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "districts": ["string"]
}
```
---------------------

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/district]()                |   `POST`     |

#### Request Body
```json
{
    "district": "string"
}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "upazillas": ["string"]
}
```
-----------------
| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/upazilla]()                |   `POST`     |

#### Request Body
```json
{
    "upazilla": "string"
}
```
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "unions": ["string"]
}
```
------------------

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/register/submit]()                |   `POST`     |

#### Request Body
```json
{
    "accountType": "string",
    "farmerType": "string",
    "nid": 1234567890,
    "name": "string",
    "dob": "02-02-2000",
    "address": "string",
    "mobile": 01234567891
}
```
### Success 
Response Code: 200 (`OK`)

#### Response Body
```json
{
    "success": true,
    "redirectURL": "string",
    "token": "string"
}
```
### Invalid Input
Response Code: 422 (`Unprocessable Entity`)

#### Response Body
```json
{
    "success": false,
    "error": "Invalid {field}"
}
```
-----------