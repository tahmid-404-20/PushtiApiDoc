# Internal Links

## Product MS

### Inventory

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/product/inventory]()    |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "user id": 12345,
>}
>```

</br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "products": [
>        {
>            "product id": 1,
>            "product name": "Sweet",
>            "quantity": 100,
>            "price": 350,
>            "unit": "kg"
>        },
>        {
>            "product id": 2,
>            "product name": "Milk",
>            "quantity": 100,
>            "price": 100,
>            "unit": "L"
>        }
>    ]
>}
>```

---

### Product Details

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/product/details]()    |   `Get`     |

>### Request
>
>#### Request Body
>
>```json
>{
>
>}
>```

</br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>[
>    {
>       "product id": 1
>       "product name": "Sweet",
>       "price": 350,
>       "unit": "kg"
>       "tax": 5
>    },
>    {
>       "product id": 2
>       "product name": "Milk",
>       "price": 100,
>       "unit": "L"
>       "tax": 5
>    }
>]
>```

---

### Update Product Details

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/product/update]()    |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "product id": 1,
>    "price": 370,
>    "tax": 5
>}
>```

</br>

>### Response - Success
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
>```json
>{
>    "message": "Product details updated successfully"
>}
>```

</br>

>### Response - Failure
>
>#### Response Code: 400 (`Bad Request`)
>
>#### Response Body
>
>```json
>{
>    "message": "Product details update failed"
>}
>```

---

## Loan MS

### Loan History

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/loan/history]()    |   `POST`     |

>### Request
>
>#### Request Body
>
>```json
>{
>    "user id": 12345,
>}
>```

</br>

>### Response
>
>#### Response Code: 200 (`OK`)
>
>#### Response Body
>
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

### Loan Requests

| API Endpoint     | HTTP Method |
| ---------------- | :---------: |
| [/loan/requests]() |    `POST`    |

> ### Request
>
> #### Request Body
>
> ```json
> {
>    "user id": 13334,
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

---

### Respond to Loan Request

#### For next stage

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/loan/response]() |   `POST`    |

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
| [/loan/accept]() |   `POST`    |

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

## Buy MS

### Buy History

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/buy/history]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "user id": 12345,
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
>               "farmer": "John Doe",
>               "avatar": "avatar23.png",
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
>               "farmer": "John Doe",
>               "avatar": "avatar23.png",
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
>               "farmer": "John Doe",
>               "avatar": "avatar23.png",
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

---

### New Transaction

#### Buy request to farmer

| API Endpoint             | HTTP Method |
| ------------------------ | :---------: |
| [/buy/request]() |   `POST`    |

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
>           "price": 100,
>       },
>       {    
>           "product_id": 24,    
>           "name": "Beef",
>           "quantity": 10,
>           "price": 900,
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

### Buy Response

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/buy/response]() |   `POST`     |

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

## Support Ticket MS

### Support Ticket History

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/support/history]() |   `POST`     |

>### Request
>
>#### Request Body
>
>    ```json
>   {
>       "id": 1234
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
>      "messages": [
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
>       ]
>   }
>    ```

</br>

>### Response - Failure
>
>#### Response Code : 404 (`Not Found`)
>
>#### Response Body
>
>    ```json
>   {
>      "success": false,
>      "message": "ID not found"
>   }
>    ```

---

### New Support Ticket

| API Endpoint              | HTTP Method |
| --- | :---: |
| [/support/add]() |   `POST`     |

> ### Request
>
> #### Request Body
>
> ```json
> {
>   "subject": "Lorem Ipsum",
>   "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incid idunt utlabore et dolore magna aliqua  quam elementum pulvinar etiam. At auctor urna nunc id cursus metus aliquam",
>   "id": 1234
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
