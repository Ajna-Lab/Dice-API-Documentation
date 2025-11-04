## SMS Services

### Send SMS

**Endpoint:** `POST /api/sms/`

**Description:** Send SMS message to recipients.

**Headers:** 
```
{
    "Authorization": "Token <YOUR_AUTH_KEY>",
    "Content-Type": "application/json"
}
```

**Request Payload:**

| Field | Required | Description |
|-------------|--------|-------------|
| phone_number | Yes |  <ul> <li>Array of strings</li> <li>List of phone numbers to send the SMS to.</li> <li>Each phone number must be between 1 and 15 characters.</li> </ul> |
| message | Yes | <ul> <li>String</li> <li>The SMS message to be sent must be between 1 and 1000 characters.</li> </ul> |
| sender_id | No | <ul><li>Optional</li></ul> |



**Request Body:**
```json
{
    "phone_number": ["+9779813012345", "9813012345", "+9779841012345", "9841012345", "0000001787"],
    "message": "Your SMS content here",
    "sender_id": ""
}
```

**Response:**
```json
{
    "status": "Queued",
    "message": "SMS Queued for delivery",
    "batch_id": "1762243228024",
    "ntc_phone_numbers": [
        "9841012345",
        "+9779841012345"
    ],
    "ncell_phone_numbers": [
        "+9779813012345",
        "9813012345"
    ],
    "invalid_phone_numbers": [
        "0000001787"
    ],
    "content": "Your SMS content here"
}
```

**Status Codes:**

- `200 OK`: SMS sent successfully
- `400 Bad Request`: Invalid request data
- `401 Unauthorized`: Invalid or missing auth token

### Send SMS With Token

**Endpoint:** `POST /api/sms-with-token/`

**Description:** Send SMS using a specific API token.


**Request Payload:**

| Field | Required | Description |
|-------------|--------|-------------|
| token | Yes | <ul> <li>UUID</li> <li>A valid token provided by the company.</li> </ul> |
| phone_number | Yes |  <ul> <li>Array of strings</li> <li>List of phone numbers to send the SMS to.</li> <li>Each phone number must be between 1 and 15 characters.</li> </ul> |
| message | Yes | <ul> <li>String</li> <li>The SMS message to be sent must be between 1 and 1000 characters.</li> </ul> |
| sender_id | No | <ul><li>Optional</li></ul> |



**Request Body:**
```json
{
    "token": "Enter your API Token here",
    "phone_number": ["+9779813012345", "9813012345", "+9779841012345", "9841012345", "0000001787"],
    "message": "Your SMS content",
    "sender_id": ""
}
```

**Response:**
```json
{
    "status": "Queued",
    "message": "SMS Queued for delivery",
    "batch_id": "1762243228024",
    "ntc_phone_numbers": [
        "9841012345",
        "+9779841012345"
    ],
    "ncell_phone_numbers": [
        "+9779813012345",
        "9813012345"
    ],
    "invalid_phone_numbers": [
        "0000001787"
    ],
    "content": "Your SMS content"
}
```

**Status Codes:**

- `200 OK`: SMS sent successfully
- `400 Bad Request`: Invalid request data
- `401 Unauthorized`: Invalid or missing auth token
- `500 Internal Server Error`: Server Encountered an Error


### Error Responses

**1. API token is not UUID**
    
Status Code: `400 Bad Request`

``` json
{
    "error": "Invalid token format. Please provide a valid UUID.",
}
```
    