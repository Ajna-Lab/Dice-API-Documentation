## Get All Batch IDs

**Endpoint:** `GET /api/batch-ids`

**Description:** Retrieve all batch IDs for SMS operations.

**Headers:**
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>"
}
```

**Response Body:**
```json
[
  {
    "sent_at": "2025-08-24T20:59:54.172833+05:45",
    "delivered_at": "2025-08-24T20:59:55.210496+05:45",
    "status": "1",
    "batch_id": "878024246730-9159"
  },
  {
    "sent_at": "2025-11-04T17:00:45.153834+05:45",
    "delivered_at": null,
    "status": "4",
    "batch_id": "881127472383-4566"
  },
  {
    "sent_at": "2025-11-04T17:00:45.185164+05:45",
    "delivered_at": null,
    "status": "SENT",
    "batch_id": "881127472383-4566"
  }
]
```

**Status Codes:**

- `200 OK`
- `404 Not Found`
- `500 Internal Server Error`


**Common Error Responses**

**1. Batch IDs not found**
    
Status Code: `404 Not Found`

``` json
{
    "error": "No batch ID found.",
}
```


**2. Error while fetching batch IDs**
    
Status Code: `500 Internal Server Error`

``` json
{
    "error": "An error occurred while fetching batch IDs.",
}
```


## Get SMS Report by `batch_id`

**Endpoint:** `GET /api/sms-report/{batch_id}/`

**Description:** Get detailed SMS report for a specific batch ID retrieved from [`GET /api/batch-ids`](sms_delivery_report.md/#get-all-batch-ids).

**Headers:**
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>"
}
```


**Path Parameters:**

- `batch_id`: The batch ID to query

For example,

```json
{
    "batch_id": "881127472383-4566"
}
```


**Response Body:**
```json
[
  {
    "message": "Burst Mode Test. Please Ignore it. @5:00",
    "recipients": [
      {
        "client_name": null,
        "client_phone": 9842271353
      }
    ],
    "sent_at": "2025-11-04T17:00:45.126760+05:45",
    "delivered_at": null,
    "status": "UNDELIVERABLE"
  },
  {
    "message": "Burst Mode Test. Please Ignore it. @5:00",
    "recipients": [
      {
        "client_name": null,
        "client_phone": 9862575511
      }
    ],
    "sent_at": "2025-11-04T17:00:45.070173+05:45",
    "delivered_at": null,
    "status": "SENT"
  },
  {
    "message": "Burst Mode Test. Please Ignore it. @5:00",
    "recipients": [
      {
        "client_name": null,
        "client_phone": 9801912821
      }
    ],
    "sent_at": "2025-11-04T17:00:45.046816+05:45",
    "delivered_at": null,
    "status": "SENT"
  },
  {
    "message": "Burst Mode Test. Please Ignore it. @5:00",
    "recipients": [
      {
        "client_name": null,
        "client_phone": 9868957429
      }
    ],
    "sent_at": "2025-11-04T17:00:45.023143+05:45",
    "delivered_at": null,
    "status": "UNDELIVERABLE"
  },
  {
    "message": "Burst Mode Test. Please Ignore it. @5:00",
    "recipients": [
      {
        "client_name": null,
        "client_phone": 9862625004
      }
    ],
    "sent_at": "2025-11-04T17:00:44.970358+05:45",
    "delivered_at": null,
    "status": "SENT"
  }
]
```

**Status Codes:**

- `200 OK`
- `404 Not Found`
- `500 Internal Server Error`


**Common Error Responses**

**1. Batch ID not found**
    
Status Code: `404 Not Found`

``` json
{
    "error": "SMS message not found.",
}
```


**2. Error while fetching batch IDs**
    
Status Code: `500 Internal Server Error`

``` json
{
    "error": "An error occurred while fetching SMS messages.",
}
```


## Get all SMS Report

**Endpoint:** `GET /api/sms-report/`

**Description:** Get delivery reports for all SMS messages.

**Headers:**
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>"
}
```

**Response Body:**
```json
{
  "count": 59,
  "next": "https://dicesms.asia/api/sms-report/?page=2",
  "previous": null,
  "results": [
    {
      "message": "Burst Mode Test. Please Ignore it. @5:00",
      "recipients": [
        {
          "client_name": null,
          "client_phone": 9801000000
        }
      ],
      "sent_at": "2025-11-04T17:00:45.185164+05:45",
      "delivered_at": null,
      "status": "SENT"
    },
    {
      "message": "Burst Mode Test. Please Ignore it. @5:00",
      "recipients": [
        {
          "client_name": null,
          "client_phone": 9843000000
        }
      ],
      "sent_at": "2025-11-04T17:00:45.153834+05:45",
      "delivered_at": null,
      "status": "UNDELIVERABLE"
    },
    {
      "message": "Burst Mode Test. Please Ignore it. @5:00",
      "recipients": [
        {
          "client_name": null,
          "client_phone": 9842000001
        }
      ],
      "sent_at": "2025-11-04T17:00:45.126760+05:45",
      "delivered_at": null,
      "status": "UNDELIVERABLE"
    },
    {
      "message": "Burst Mode Test. Please Ignore it. @5:00",
      "recipients": [
        {
          "client_name": null,
          "client_phone": 9805000000
        }
      ],
      "sent_at": "2025-11-04T17:00:45.092500+05:45",
      "delivered_at": null,
      "status": "SENT"
    },
    {
      "message": "Burst Mode Test. Please Ignore it. @5:00",
      "recipients": [
        {
          "client_name": null,
          "client_phone": 98625000000
        }
      ],
      "sent_at": "2025-11-04T17:00:45.070173+05:45",
      "delivered_at": null,
      "status": "SENT"
    },
}
```

**Status Codes:**

- `200 OK`
- `404 Not Found`
- `500 Internal Server Error`


**Common Error Responses**

**1. Error while fetching batch IDs**
    
Status Code: `500 Internal Server Error`

``` json
{
    "error": "An error occurred while fetching SMS reports.",
}
```


## Get SMS Metrics

**Endpoint:** `GET api/metrics/snapshot/`

**Description:** Get metric snapshot of SMS messages.

**Permission:** User has to be a staff, i.e. `is_staff = True`

**Headers:**
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>"
}
```

**Response Body:**
```json
{
  "sms:metrics:enqueue:d:20251105": 3,
  "sms:metrics:enqueue:op:NCELL:d:20251105": 3,
  "sms:metrics:enqueue": 3,
  "sms:metrics:enqueue:op:NCELL": 3
}
```

**Status Codes:**

- `200 OK`
- `403 Forbidden`
- `500 Internal Server Error`
