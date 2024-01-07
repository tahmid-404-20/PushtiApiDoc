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
>       "Sales History": [
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
>       ]
>   }
>    ```

</br>

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

</br>

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

</br>

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

</br>

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

</br>

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

</br>

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

</br>

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

</br>

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
>   [
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

</br>

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

</br>

---
