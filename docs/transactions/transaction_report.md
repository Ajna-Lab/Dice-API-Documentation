# Credit Purchase Transaction Report


**Endpoint:** `GET /api/transaction/report/`

**Description:** Get transaction reports for credits purchase.

**Headers:**
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>"
}
```

**Response Body:**

```json
{
    "amount": 100,
    "remarks": "",
    "currency": "NPR",
    "status": "S",
    "transaction_date": "2025-10-29T13:03:32.701316+05:45",
    "service_charge": 0
}
```

**Status Codes:**

- `200 OK`
- `500 Internal Server Error`

**Common Error Responses**

**1. Batch ID not found**
    
Status Code: `404 Not Found`

``` json
{
    "message": "No transactions found.",
}
```


**2. Error while fetching batch IDs**
    
Status Code: `500 Internal Server Error`

``` json
{
    "error": "An error occurred while fetching transactions.",
}
```




