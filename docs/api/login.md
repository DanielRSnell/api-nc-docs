# Authentication API (Keycloak Implementation)

**Note: This document is for reference only and not a required handoff document. The actual implementation will use Keycloak for authentication.**

This document outlines the authentication approach for the Nightcrawler Dashboard.

## Base URL

```
/api/auth
```

## Endpoints

### Login

Authenticates a user and returns a session token.

**Endpoint:** `POST /api/auth/login`

**Request Body:**

```json
{
  "username": "admin@email.com",
  "password": "password123"
}
```

**Response:**

```json
{
  "success": true,
  "user": {
    "id": "user-1",
    "username": "admin@email.com",
    "name": "Admin User",
    "role": "admin",
    "avatar": "/assets/avatars/admin.png"
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

### Logout

Invalidates the current session token.

**Endpoint:** `POST /api/auth/logout`

**Headers:**
- `Authorization: Bearer {token}`

**Response:**

```json
{
  "success": true,
  "message": "Logged out successfully"
}
```

### Get Current User

Retrieves information about the currently authenticated user.

**Endpoint:** `GET /api/auth/me`

**Headers:**
- `Authorization: Bearer {token}`

**Response:**

```json
{
  "id": "user-1",
  "username": "admin@email.com",
  "name": "Admin User",
  "role": "admin",
  "avatar": "/assets/avatars/admin.png"
}
```

### Refresh Token

Refreshes an expired token.

**Endpoint:** `POST /api/auth/refresh`

**Headers:**
- `Authorization: Bearer {token}`

**Response:**

```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

## Data Models

### User Object

| Field | Type | Description |
|-------|------|-------------|
| id | string | Unique identifier for the user |
| username | string | User's email address used for login |
| name | string | User's display name |
| role | string | User's role (admin, user, etc.) |
| avatar | string | URL to the user's avatar image |

## Error Responses

All endpoints may return the following error responses:

### 400 Bad Request

```json
{
  "success": false,
  "error": "Bad Request",
  "message": "Invalid request parameters"
}
```

### 401 Unauthorized

```json
{
  "success": false,
  "error": "Unauthorized",
  "message": "Invalid credentials"
}
```

### 403 Forbidden

```json
{
  "success": false,
  "error": "Forbidden",
  "message": "Insufficient permissions to perform this action"
}
```

### 500 Internal Server Error

```json
{
  "success": false,
  "error": "Internal Server Error",
  "message": "An unexpected error occurred"
}
```

## Authentication Flow with Keycloak

The Nightcrawler Dashboard will implement authentication using Keycloak, which provides:

1. Single Sign-On (SSO) capabilities
2. Identity and Access Management
3. Social login integration
4. Multi-factor authentication
5. User federation
6. Standard protocols support (OAuth 2.0, OpenID Connect, SAML)

The implementation details and specific endpoints will be determined during the Keycloak integration phase. The example endpoints in this document are for reference only and will be replaced by the Keycloak authentication flow.
