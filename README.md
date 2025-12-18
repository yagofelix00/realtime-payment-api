
---

# ⚡ Realtime Payment API (PIX)

A real-time payment API built with **Flask**, **SQLite**, and **WebSockets**, designed to handle **PIX payments**, generate **QR Codes**, and provide **real-time payment confirmation** updates to clients.

This project simulates a complete PIX payment flow, including payment creation, expiration handling, webhook confirmation, QR Code delivery, and live status updates via WebSockets.

---

## 📌 Overview

The **RealtimePaymentAPI** provides a back-end service responsible for:

* 💳 Creating PIX payments
* ⏱️ Managing payment expiration
* 🧾 Storing payments in a database
* 🧠 Integrating with a PIX service layer
* 🖼️ Serving QR Code images
* 🔔 Receiving payment confirmations via webhook
* ⚡ Notifying clients in real time using WebSockets

The API is designed to simulate real-world payment systems and asynchronous confirmation flows.

---

## 🚀 Features

### **1. PIX Payment Creation**

* Creates a payment using a REST endpoint
* Generates an expiration time (30 minutes)
* Stores payment data in a database
* Integrates with a PIX service to generate a QR Code

---

### **2. QR Code Delivery**

* Provides a public endpoint to retrieve the QR Code image
* Allows front-end clients to display the PIX code easily

---

### **3. Payment Confirmation via Webhook**

* Receives confirmation requests from an external service
* Validates payment ID and value
* Updates payment status in the database

---

### **4. Real-Time Notification (WebSockets)**

* Notifies connected clients when a payment is confirmed
* Uses **Flask-SocketIO** for real-time communication

---

### **5. Payment Status Page**

* Renders HTML pages for:

  * Pending payments
  * Confirmed payments
* Displays QR Code and payment details dynamically

---

### **6. Fully Asynchronous Flow**

* Payment creation and confirmation are decoupled
* Clients receive updates instantly without polling

---

## 📂 Project Structure

```
realtime-payment-api/
│
├── app.py
├── requirements.txt
├── README.md
│
├── db_models/
│   ├── payment.py
│   └── __pycache__/
│
├── repository/
│   ├── database.py
│   └── __pycache__/
│
├── payments/
│   ├── pix.py
│   └── __pycache__/
│
├── instance/
│   └── database.db
│
├── static/
│   ├── css/
│   ├── img/
│   └── template_img/
│
├── templates/
│   ├── payment.html
│   ├── confirmed_payment.html
│   └── 404.html
│
├── tests/
│
└── venv/

```

---

## 📸 API Flow Example

This project follows the flow below:

1. Client creates a PIX payment
2. API generates a QR Code and stores payment data
3. Client accesses the payment page
4. External service confirms the payment via webhook
5. Client receives real-time confirmation via WebSocket

*(Optional: add screenshots or GIFs showing the flow)*

---

## ▶️ How to Run the Project

### 📥 1. Clone the Repository

```bash
git clone https://github.com/yagofelix00/realtime-payment-api.git
cd realtime-payment-api
```

---

### 📦 2. Install Dependencies

```bash
pip install -r requirements.txt
```

> Python 3.10+ recommended.

---

### ⚙️ 3. Configure the Environment

Make sure you have:

* Python installed
* Virtual environment activated (optional but recommended)

The project uses **SQLite**, so no external database setup is required.

---

### ▶️ 4. Run the Application

```bash
python app.py
```

The server will start at:

```
http://127.0.0.1:5000
```

---

## 🔌 API Endpoints

### ➕ Create PIX Payment

`POST /payments/pix`

```json
{
  "value": 100.0
}
```

---

### 🖼️ Get QR Code

`GET /payments/pix/qr_code/<file_name>`

---

### ✅ Confirm Payment (Webhook)

`POST /payments/pix/confirmation`

```json
{
  "bank_payment_id": "abc123",
  "value": 100.0
}
```

---

### 📄 Payment Page

`GET /payments/pix/<payment_id>`

---

## 🛠️ Technologies Used

* **Python**
* **Flask**
* **Flask-SocketIO**
* **SQLAlchemy**
* **SQLite**
* **HTML / Jinja2**
* **REST APIs**
* **WebSockets**

---

## 🔮 Future Improvements

* Add authentication and authorization
* Implement payment expiration background jobs
* Add unit and integration tests
* Replace SQLite with PostgreSQL
* Add Docker support
* Add API documentation with Swagger/OpenAPI
* Improve error handling and logging

---

## 📝 Notes

* This project simulates a PIX payment flow for learning purposes
* All payment data is fictional
* Designed to practice:

  * REST APIs
  * Real-time communication
  * Database persistence
  * Webhooks
  * Payment system concepts

---

## 👤 Author

**Yago Félix**  
💼 Python Developer — Back-end | Data Analytics | Full Stack  
🔍 Focused on building scalable back-end systems, APIs, and real-time applications using Python.  
📊 Interested in Back-end Development, Data Analytics, SQL, APIs, and system automation.  
🔗 More projects: [https://github.com/yagofelix00](https://github.com/yagofelix00)  

---
