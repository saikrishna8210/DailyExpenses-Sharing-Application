A robust backend service for managing and splitting daily expenses among users. This application allows users to split expenses using different methods (equal, exact, or percentage-based) and generates detailed balance sheets.

## 🌟 Features

### User Management
- Create and manage user profiles
- Store essential user details (email, name, mobile number)
- User authentication and authorization
- Input validation for user data

### Expense Management
- Add and track expenses
- Multiple splitting methods:
  1. **Equal Split**: Divide expenses equally among participants
  2. **Exact Split**: Specify exact amounts for each participant
  3. **Percentage Split**: Divide based on percentage allocation

### Balance Sheet
- View individual expense reports
- Generate overall expense summaries
- Download balance sheets in multiple formats
- Real-time balance calculations

## 🛠️ Technology Stack

- **Backend**: Node.js with Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **Documentation**: Swagger/OpenAPI
- **Testing**: Jest
- **Validation**: Joi

## 🔑 API Endpoints

### User Management
```
POST   /api/users           - Create new user
GET    /api/users/:id       - Get user details
PUT    /api/users/:id       - Update user
DELETE /api/users/:id       - Delete user
```

### Expense Management
```
POST   /api/expenses              - Add new expense
GET    /api/expenses/:id          - Get expense details
GET    /api/expenses/user/:userId - Get user expenses
GET    /api/expenses/summary      - Get expense summary
GET    /api/expenses/download     - Download balance sheet
```

## 💡 Usage Examples

### 1. Equal Split Example
```json
{
  "amount": 3000,
  "paidBy": "user123",
  "splitType": "EQUAL",
  "participants": ["user123", "user456", "user789"]
}
// Result: Each user owes 1000
```

### 2. Exact Split Example
```json
{
  "amount": 4299,
  "paidBy": "user123",
  "splitType": "EXACT",
  "splits": [
    {"userId": "user456", "amount": 799},
    {"userId": "user789", "amount": 2000},
    {"userId": "user123", "amount": 1500}
  ]
}
```

### 3. Percentage Split Example
```json
{
  "amount": 1000,
  "paidBy": "user123",
  "splitType": "PERCENTAGE",
  "splits": [
    {"userId": "user123", "percentage": 50},
    {"userId": "user456", "percentage": 25},
    {"userId": "user789", "percentage": 25}
  ]
}
```

## 🧪 Testing

Run the test suite:
```bash
npm test                 # Run all tests
npm run test:unit       # Run unit tests
npm run test:integration # Run integration tests
```

## 📊 Performance Optimization

- MongoDB indexing for faster queries
- Caching implementation using Redis
- Pagination for large datasets
- Batch processing for bulk operations




