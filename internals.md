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
>    "user type": "Agent",
>    "union": "Kamalpur",
>}
>```

>[!NOTE]
>**user type** can be one of the following:
>
>* Farmer
>* SME
>* Agent

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
