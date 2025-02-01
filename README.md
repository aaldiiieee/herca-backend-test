# Herca API Backend

This is the backend for the Herca application, providing RESTful APIs to handle sales transactions, payment processing, and payment history.

## Features
- Record payments for sales transactions.
- Retrieve payment history.

## Installation

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/herca-backend.git
cd herca-backend
```

### Step 2: Install Dependencies
```bash
npm install
```

### Step 3: Start the Server
```bash
npm run start
```

## API Endpoints

#### Get all payments
```bash
  GET /api/payment/get-payments
```
Response:

```json
[
  {
    "transactionId": 1,
    "amount": 1000,
    "date": "2025-01-31T08:00:00.000Z"
  }
]
```
#### Add a Payment
```bash
  POST /api/payment/make-payment
```

Request Body:

```json
{
  "transactionId": 1,
  "amount": 1000
}
```

Response:

```json
{
  "message": "Payment recorded",
  "payments": [
    {
      "transactionId": 1,
      "amount": 1000,
      "date": "2025-01-31T08:00:00.000Z"
    }
  ]
}
```