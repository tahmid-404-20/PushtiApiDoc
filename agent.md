# Agent

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

</br>

---

## Loan
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
>        "img_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
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
>        "img_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
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
>        "img_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
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
>        "img_link": "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.pe",
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

</br>

---

### Respond to Loan Request

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
>   "next": True,
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

</br>

---
