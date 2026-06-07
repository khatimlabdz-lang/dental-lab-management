# REST API Documentation - Dental Lab Management System

## Base URL
```
http://localhost:3000/api/v1
```

## Authentication
All endpoints require JWT token:
```
Authorization: Bearer <jwt_token>
```

## Response Format
```json
{
  "success": true,
  "data": {},
  "message": "Success",
  "timestamp": "2024-01-01T00:00:00Z"
}
```

## Core Endpoints

### Customers
- `GET /customers` - List customers
- `POST /customers` - Create customer
- `GET /customers/:id` - Get customer details
- `PUT /customers/:id` - Update customer

### Cases
- `GET /cases` - List cases
- `POST /cases` - Create case
- `GET /cases/:id` - Get case details
- `PUT /cases/:id` - Update case
- `PATCH /cases/:id/status` - Update case status

### Digital Files
- `POST /cases/:id/files` - Upload file
- `GET /cases/:id/files` - List case files
- `GET /cases/:id/files/:file_id/download` - Download file
- `DELETE /cases/:id/files/:file_id` - Delete file

### Workflow
- `GET /cases/:id/workflow` - Get case workflow
- `PATCH /workflow-steps/:id` - Update workflow step

### Inventory
- `GET /inventory` - List inventory
- `POST /inventory` - Create inventory item
- `GET /inventory/:id` - Get item details
- `PATCH /inventory/:id` - Update item

### Employees
- `GET /employees` - List employees
- `POST /employees` - Create employee
- `GET /employees/:id` - Get employee details

### Billing
- `POST /quotes` - Create quote
- `POST /invoices` - Create invoice
- `GET /invoices` - List invoices

### Reports
- `GET /reports/dashboard` - Dashboard summary
- `GET /reports/production` - Production report
- `GET /reports/revenue` - Revenue report

## Error Responses
- `400 Bad Request` - Validation error
- `401 Unauthorized` - Authentication required
- `403 Forbidden` - Insufficient permissions
- `404 Not Found` - Resource not found
- `500 Internal Server Error` - Server error

## Rate Limiting
- 100 requests per minute per user
- Headers: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`
