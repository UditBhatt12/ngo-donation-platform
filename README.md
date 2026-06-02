# NGO Registration and Donation Management System

A comprehensive web application for managing NGO registrations and processing donations with integrated payment gateway support.

**Tech Stack:** Node.js, Express.js, MongoDB, EJS, PayHere

---

## 🎯 Features

### 👤 User Features

* Secure user registration and login system with password hashing
* Donation processing through the PayHere payment gateway
* Personal dashboard with donation history and transaction status
* PDF receipt generation for successful donations
* Profile management and password updates

### 🛡️ Admin Features

* Comprehensive admin dashboard with statistics and analytics
* User management and role filtering
* Donation monitoring with sorting and filtering capabilities
* Real-time notifications for registrations and donations
* Donation analytics and trend visualization
* CSV export functionality
* PDF report generation

### 👑 Superadmin Features

* Promote users to admin role
* Remove admin privileges
* Full system management access

---

## 🛠️ Technologies Used

| Category        | Technology                 |
| --------------- | -------------------------- |
| Backend         | Node.js, Express.js        |
| Database        | MongoDB Atlas              |
| Template Engine | EJS                        |
| Authentication  | Express Sessions, bcryptjs |
| Payment Gateway | PayHere                    |
| PDF Generation  | PDFKit                     |
| Security        | MD5 Hash Verification      |

---

## 📋 Prerequisites

Before running the project, ensure you have:

* Node.js (v14 or higher)
* npm
* MongoDB Atlas account (or local MongoDB)
* PayHere Merchant Account

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ngo-donation-platform.git
cd ngo-donation-platform
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create Environment Variables

Create a `.env` file in the root directory:

```env
MONGO_URI=your_mongodb_connection_string
SESSION_SECRET=your_secret_key
PAYHERE_MERCHANT_ID=your_payhere_merchant_id
PAYHERE_MERCHANT_SECRET=your_payhere_merchant_secret
PORT=3000
```

### 4. Start the Server

```bash
node server.js
```

### Development Mode

```bash
nodemon server.js
```

### 5. Open the Application

```text
http://localhost:3000
```

---

## ⚙️ Configuration

### Environment Variables

| Variable                | Description               |
| ----------------------- | ------------------------- |
| MONGO_URI               | MongoDB connection string |
| SESSION_SECRET          | Session encryption secret |
| PAYHERE_MERCHANT_ID     | PayHere merchant ID       |
| PAYHERE_MERCHANT_SECRET | PayHere merchant secret   |
| PORT                    | Server port               |

---

## 💳 PayHere Integration

1. Create a PayHere merchant account.
2. Configure the return URL:

```text
http://your-domain.com/payment/success
```

3. Configure the webhook URL:

```text
http://your-domain.com/payment/notify
```

4. Use sandbox mode during testing.

---

## 📁 Project Structure

```text
ngo-donation-platform/
│
├── public/
│   └── images/
│       └── nss-logo.jpg
│
├── views/
│   ├── index.ejs
│   ├── login.ejs
│   ├── register.ejs
│   ├── dashboard.ejs
│   ├── admin.ejs
│   ├── settings.ejs
│   └── payment_gateway.ejs
│
├── server.js
├── package.json
├── package-lock.json
├── .env
└── README.md
```

---

## 🔐 User Roles

### User

* Make donations
* View donation history
* Download receipts
* Update profile settings

### Admin

* All user privileges
* Access admin dashboard
* Manage users and donations
* Generate reports
* View notifications

### Superadmin

* All admin privileges
* Promote users to admin
* Remove admin privileges

---

## 📡 API Endpoints

### Authentication

| Method | Endpoint  | Description       |
| ------ | --------- | ----------------- |
| GET    | /         | Home Page         |
| GET    | /register | Registration Page |
| POST   | /register | Register User     |
| GET    | /login    | Login Page        |
| POST   | /login    | User Login        |
| GET    | /logout   | Logout User       |

### User Routes

| Method | Endpoint     |
| ------ | ------------ |
| GET    | /dashboard   |
| GET    | /settings    |
| POST   | /settings    |
| GET    | /receipt/:id |

### Payment Routes

| Method | Endpoint         |
| ------ | ---------------- |
| POST   | /get-hash        |
| GET    | /payment/success |
| POST   | /payment/notify  |

### Admin Routes

| Method | Endpoint                   |
| ------ | -------------------------- |
| GET    | /admin                     |
| GET    | /admin/clear-notifications |
| GET    | /admin/report-pdf          |
| GET    | /admin/export              |

### Superadmin Routes

| Method | Endpoint                     |
| ------ | ---------------------------- |
| POST   | /superadmin/make-admin/:id   |
| POST   | /superadmin/remove-admin/:id |

---

## 💳 Payment Flow

1. User enters donation amount.
2. Frontend requests payment hash.
3. Backend generates MD5 hash.
4. PayHere payment popup opens.
5. User completes payment.
6. PayHere redirects to success page.
7. Webhook notification updates donation status.
8. Admin receives notification.

---

## 🔒 Security Features

* Password hashing with bcryptjs
* Session-based authentication
* Role-Based Access Control (RBAC)
* MD5 payment verification
* Protected routes with middleware
* Input validation and sanitization

---

## 📊 Database Models

### User

```javascript
{
  name,
  email,
  password,
  role,
  registeredAt
}
```

### Donation

```javascript
{
  userId,
  amount,
  status,
  transactionId,
  orderId,
  date
}
```

### Notification

```javascript
{
  message,
  type,
  date
}
```

---

## 🐛 Troubleshooting

### MongoDB Connection Error

* Verify `MONGO_URI`
* Check Atlas IP whitelist
* Confirm internet connectivity

### PayHere Issues

* Verify merchant credentials
* Ensure sandbox mode is enabled
* Check webhook and return URLs

### Session Issues

* Clear browser cookies
* Verify session secret

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push the branch
5. Open a Pull Request

---

## 📄 License

Licensed under the ISC License.

---

## 👥 Contributors

* Udit Prakash Bhatt
* Prathamesh Amrutkar

---

## 🙏 Acknowledgments

* PayHere
* MongoDB Atlas
* Express.js Community

---


