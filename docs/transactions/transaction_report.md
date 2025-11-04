# Transaction Report


**Endpoint:** `GET /api/transaction/report/`

**Description:** Get transaction reports for credits purchase.

**Headers:**
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>"
}
```

**Response:**
```json
{
  "amount": 0,
  "remarks": "string",
  "currency": "string",
  "status": "S",
  "transaction_date": "2025-11-04T10:23:02.315Z",
  "service_charge": 0
}
```

**Response Sample:**
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