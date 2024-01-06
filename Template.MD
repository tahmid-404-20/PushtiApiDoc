# Template

## Farmer Module

### Dashboard

#### API Endpoint: [/farmer/{id}/dashboard]()

#### HTTP Method: `GET`

| API Endpoint              | HTTP Method |
| ------------------------- | :---------: |
| [/farmer/{id}/dashboard]() |   `GET`     |

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
>Or just use N/A like this
>
>#### Request Body : N/A

</br>

>### Response
>
>If you need to specify whether or not it was a success or failure, use this instead of previous line and use another code block for the failure one
>
>### Response - Success
>
>#### Response Code : 200 (`OK`)
>
>#### Response Body
>
>    ```json
>   {
>       "name": "John Doe",
>       "nid": 123456789,
>       "type": "Dairy",
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
>               "date": "2020-01-01",
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
>               "date": "2020-01-02",
>               "amount": 1500,
>               "Objects": [
>                   {
>                       "name": "Meat",
>                       "quantity": 5,
>                       "price": 1500
>                   }
>               ],
>               "status": "Accepted"
>           }
>       ]
>   }
>    ```
