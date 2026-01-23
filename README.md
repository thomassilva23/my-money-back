# My Money - Backend

REST API for the My Money personal finance application.

## Technologies

- Node.js
- Express
- MongoDB (Mongoose 6)
- JWT Authentication
- Bcrypt

## Requirements

- Node.js 14+
- MongoDB Atlas account or local MongoDB instance

## Setup

1. Install dependencies:
```bash
npm install
```

2. Configure environment variables in `src/.env`:
```javascript
module.exports = {
    authSecret: 'your-secret-key',
    mongoUri: 'your-mongodb-connection-string'
}
```

3. Run in development mode:
```bash
npm run dev
```

4. Run in production:
```bash
npm run production
```

## API Endpoints

### Open Routes (`/oapi`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/oapi/signup` | Create new user |
| POST | `/oapi/login` | Authenticate user |
| POST | `/oapi/validateToken` | Validate JWT token |

### Protected Routes (`/api`)

Requires `Authorization` header with valid JWT token.

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/billingCycles` | List billing cycles |
| POST | `/api/billingCycles` | Create billing cycle |
| PUT | `/api/billingCycles/:id` | Update billing cycle |
| DELETE | `/api/billingCycles/:id` | Delete billing cycle |

## Project Structure

```
src/
  api/
    billingCycle/    # Billing cycle model and service
    user/            # User model and auth service
  config/
    auth.js          # JWT authentication middleware
    cors.js          # CORS configuration
    database.js      # MongoDB connection
    routes.js        # API routes
    server.js        # Express server setup
  loader.js          # Application entry point
```

## Password Requirements

Passwords must contain:
- 6-20 characters
- At least one uppercase letter
- At least one lowercase letter
- At least one number
- At least one special character (@, #, $, %)
