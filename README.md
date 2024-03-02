---

# ProLLM Image Generator API

## Front-end Usage

To use the ProLLM Image Generator API, send a GET request to the `/prompt` endpoint with the following query parameters:

- `prompt`: The prompt for generating the image.
- `ip`: The user's IP address.

Example Request:
```
GET /prompt?prompt=beautiful%20landscape&ip=192.168.0.1
```

## Responses

### Success Response:
- **Code**: 200
- **Message**: Image URL (Google Storage API)

Example Response:
```json
{
  "code": 200,
  "url": "https://storage.googleapis.com/pai-images/image123.jpeg"
}
```

### Bad Request:
- **Code**: 400
- **Message**: Bad request. Please check your input parameters.

Example Response:
```json
{
  "code": 400,
  "error": "Bad request. Please check your input parameters."
}
```

### Unauthorized:
- **Code**: 401
- **Message**: Unauthorized. Please provide valid credentials.

Example Response:
```json
{
  "code": 401,
  "error": "Unauthorized. Please provide valid credentials."
}
```

### Forbidden:
- **Code**: 403
- **Message**: Daily limit exceeded for free users. Upgrade to pro for unlimited access.

Example Response:
```json
{
  "code": 403,
  "error": "Daily limit exceeded for free users. Upgrade to pro for unlimited access."
}
```

### Internal Server Error:
- **Code**: 500
- **Message**: Internal server error. Please try again later.

Example Response:
```json
{
  "code": 500,
  "error": "Internal server error. Please try again later."
}
```

---