# API Authentication

### Custom Auth Token

**Endpoint:** `POST /api/api-token-auth/`

**Description:** Obtain authentication token for API access.

**Request Body:**
```json
{
    "username": "your_username",
    "password": "your_password"
}
```

**Response:**
```json
{
    "token": "<YOUR_AUTH_KEY>"
}
```

**Status Codes:**

- `200 OK` - Authentication successful
- `400 Bad Request` - Invalid credentials

---