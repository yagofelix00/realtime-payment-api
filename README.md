
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

