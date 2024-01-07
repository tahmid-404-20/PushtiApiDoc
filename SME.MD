# SME

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
>       "Sales History": [
>           {
>               "tid": 123456789,    
>               "date": new Date('2022-10-31T11:00:00Z'),
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
>               "date": new Date('2022-10-31T15:00:00Z'),
>               "amount": 1500,
>               "Objects": [
>                   {
>                       "name": "Ghee",
>                       "quantity": 5,
>                       "price": 1500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ],
>       "Buy History": [
>           {
>               "tid": 123456789,    
>               "date": new Date('2022-10-31T09:00:00Z'),
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
>               "date": new Date('2022-10-31T09:00:00Z'),
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
>       ]
>   }
>    ```

</br>

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
>           "start date": new Date('2022-10-31T09:00:00Z'),    
>           "amount": 10000,
>           "remaining": 5000,
>           "interest": 10,
>           "status": active,
>       },
>       "loan history": [
>           {
>               "start date": new Date('2022-10-31T09:00:00Z'),
>               "end date": new Date('2022-10-31T09:00:00Z'),
>               "amount": 10000,
>               "status": completed
>           },
>           {
>               "start date": new Date('2022-10-31T09:00:00Z'),
>               "end date": new Date('2022-10-31T09:00:00Z'),
>               "amount": 15000,
>               "status": rejected
>           }
>       ]
>   }
>    ```

</br>

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

</br>

---
