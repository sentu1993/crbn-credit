# Authentication

The CRBN Credit API uses standard Bearer Token authentication via HTTP headers. To access the API, you must request an API key through the [Client Dashboard](/client-dashboard) (requires institutional beta access).

## Securing Your API Key

Your API key carries significant privileges, particularly if you have enabled programmatic retirements (which move real funds and carbon assets).
- **Never** embed your API key directly in frontend code.
- **Always** store your API key in environment variables securely.
- Rotate your keys every 90 days via the dashboard.

## Passing the Key in Requests

Include your API key in the `Authorization` header of every request:

```http
GET /v1/market/prices HTTP/1.1
Host: api.crbn.credit
Authorization: Bearer sk_live_your_api_key_here
```

## Error Handling

If authentication fails, the API will return standard HTTP status codes:
- `401 Unauthorized`: API key is missing, invalid, or expired.
- `403 Forbidden`: Your API key does not have the necessary permissions (e.g., trying to execute a retirement with a read-only key).
- `429 Too Many Requests`: You have exceeded your rate limit. See rate limit headers in the response for cooldown periods.
