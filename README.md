**🕉️ श्री गणेशाय नम**ः

# 🛕 DivyaCloak

### Sacred Temple Cloakroom & Footfall Management System

**DivyaCloak** is a full-stack digital safe-keep and crowd-management platform designed for Indian temples and pilgrimage shrines.

The platform helps devotees securely deposit belongings that are not permitted inside temples—such as **shoes, phones, bags, and belts**—while providing temple staff with a centralized system to manage storage, payments, digital tokens, rack allocation, and visitor footfall.

> **Secure your belongings. Simplify your Darshan. Manage temple crowds smarter.**

---

## ✨ Key Features

### 🙏 Devotee Booking

Devotees can quickly register and create a safe-keep booking for their belongings.

Supported items:

| Item     | Price |
| -------- | ----: |
| 👟 Shoes |    ₹5 |
| 📱 Phone |   ₹10 |
| 👜 Bag   |   ₹10 |
| 🧢 Belt  |    ₹5 |

The pricing system is designed to be simple, transparent, and suitable for high-volume temple environments.

---

### 🎫 Digital QR Pass

After completing a booking, the system generates a **Digital QR Pass** containing:

* Unique booking/token ID
* QR code
* 4-digit security PIN
* Deposited item details
* Rack/storage information
* Booking information

The QR pass can be used during pickup to help staff quickly locate the devotee's belongings.

---

### 🏪 Staff POS Kiosk

Temple staff can manage cloakroom operations through a dedicated POS-style interface.

Features include:

* New booking creation
* Item registration
* Payment tracking
* Rack assignment
* Token generation
* Item pickup
* Booking status management
* Staff-friendly workflow

---

### 🗄️ 36-Rack Warehouse Map

The system includes a visual **36-rack storage map**.

Staff can easily identify:

* 🟢 Available racks
* 🔴 Occupied racks
* 🟡 Reserved/processing racks
* 📦 Stored items

This reduces manual searching and improves the speed of item collection.

---

### 🚶 Real-Time Temple Footfall Counter

Temple staff can record visitor footfall using quick counters:

```text
+1   +5   +10
```

This allows staff to quickly update the number of visitors entering the temple without manually entering large numbers.

---

### 📊 Crowd Analytics

The dashboard provides **7-day footfall trend analytics** to help temple administrators understand visitor patterns.

Analytics can be used to identify:

* Peak visiting periods
* High-footfall days
* Low-footfall days
* Crowd trends
* Operational requirements

---

### 🤖 DivyaSeva AI Assistant

DivyaCloak includes **DivyaSeva**, an AI-style temple assistant supporting:

* 🇮🇳 Hindi
* 🇬🇧 English

The assistant is designed to help devotees with common cloakroom and temple-related questions.

Example:

```text
Devotee:
Where can I deposit my phone?

DivyaSeva:
You can deposit your phone at the DivyaCloak safe-keep counter.
The standard phone storage charge is ₹10.
```

### ⚠️ AI Fallback

The current MVP includes a **rule-based intelligent fallback system** for cloakroom pricing and rules.

This ensures that core functionality continues to work even when an external LLM service is unavailable or exceeds its API budget.

> Note: The Emergent LLM upstream budget was exceeded during development, so the MVP currently relies on the rule-based fallback for these functions.

---

# 🏗️ System Overview

```text
                    ┌──────────────────────┐
                    │      DEVOTEE         │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Booking System     │
                    │  Items + Payment     │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   QR Digital Pass    │
                    │   + Security PIN     │
                    └──────────┬───────────┘
                               │
                               ▼
                 ┌─────────────────────────────┐
                 │     Temple Cloakroom       │
                 │                             │
                 │  36-Rack Storage System    │
                 └──────────────┬──────────────┘
                                │
                    ┌───────────┴───────────┐
                    ▼                       ▼
             ┌──────────────┐       ┌──────────────┐
             │ Staff POS    │       │ Pickup Desk  │
             │ Kiosk        │       │ QR + PIN     │
             └──────────────┘       └──────────────┘

                         ┌─────────────────┐
                         │ Admin Dashboard │
                         ├─────────────────┤
                         │ Footfall        │
                         │ Analytics       │
                         │ Rack Status     │
                         │ Bookings        │
                         └─────────────────┘
```

---

# 👥 User Roles

## Devotee

Devotees can:

* Register/book a cloakroom service
* Select items
* View pricing
* Receive a digital QR pass
* Use their security PIN
* Retrieve their belongings

## Staff

Staff members can:

* Create/manage bookings
* Assign storage racks
* Manage stored items
* Process pickups
* Update footfall
* View rack availability

## Administrator

Administrators can monitor:

* Total bookings
* Cloakroom usage
* Rack utilization
* Visitor footfall
* 7-day crowd trends
* Operational performance

---

# 🔄 Main Workflow

### Step 1 — Devotee Registration

The devotee enters the required information.

### Step 2 — Select Items

The devotee selects belongings such as:

```text
☑ Phone
☑ Shoes
☑ Bag
☐ Belt
```

### Step 3 — Calculate Charges

The system automatically calculates the total amount.

Example:

```text
Phone      ₹10
Shoes       ₹5
Bag        ₹10
----------------
Total      ₹25
```

### Step 4 — Generate Digital Pass

The system generates:

```text
Booking ID
     +
QR Code
     +
4-Digit Security PIN
     +
Rack Number
```

### Step 5 — Store Belongings

Staff receives the items and stores them in the assigned rack.

### Step 6 — Darshan

The devotee can proceed for Darshan without carrying restricted belongings.

### Step 7 — Pickup

After Darshan, the devotee presents the QR pass/PIN.

Staff verifies the booking and retrieves the belongings.

---

# 📊 Dashboard

The administration dashboard is designed to provide a quick operational overview.

Example metrics:

```text
┌────────────────┬────────────────┐
│ Today's Visitors│ Active Bookings│
│      1,250      │       86       │
├────────────────┼────────────────┤
│ Occupied Racks │ Available Racks │
│      24/36      │       12       │
└────────────────┴────────────────┘
```

The dashboard can also display the **7-day visitor trend**.

---

# 🔐 Security Features

The MVP includes multiple mechanisms to improve safe-keep security:

* Unique booking/token IDs
* QR-based digital passes
* 4-digit security PIN
* Rack assignment
* Booking status tracking
* Staff-controlled pickup
* Separation of booking and storage information

> For a production deployment, additional authentication, authorization, audit logging, encryption, payment verification, and operational security controls should be added.

---

# 🧠 Intelligent Rule-Based System

The MVP uses a rule-based fallback for important cloakroom logic.

For example:

```text
IF item = phone
    price = ₹10

IF item = shoes
    price = ₹5

IF item = bag
    price = ₹10

IF item = belt
    price = ₹5
```

This approach ensures that basic cloakroom functionality does not depend completely on an external AI service.

---

# 🚀 Future Roadmap

The next version of DivyaCloak can include:

### 📲 SMS Notifications

Automatically send:

* Booking confirmation
* QR/token receipt
* Pickup reminder
* Successful pickup confirmation

### 💬 WhatsApp Integration

Send the digital token directly through WhatsApp.

Example:

```text
🙏 DivyaCloak

Your safe-keep booking is confirmed.

Token: DC-10284
Items: Phone + Shoes
Rack: R-17
PIN: ****

Have a peaceful Darshan 🛕
```

### 🔗 One-Tap Pickup Link

After Darshan, devotees could receive a notification containing a pickup link.

Example:

```text
Your belongings are ready for pickup.

[ START PICKUP ]
```

### 🔒 Electronic Locker Integration

Integrate physical electronic lockers using hardware relays.

Potential architecture:

```text
DivyaCloak
     │
     ▼
Backend API
     │
     ▼
IoT / Locker Controller
     │
     ▼
Electronic Relay
     │
     ▼
Physical Locker
```

### 📈 Advanced Analytics

Future analytics could include:

* Hourly footfall
* Peak-hour prediction
* Rack utilization
* Average storage duration
* Daily revenue
* Item-wise demand
* Festival-season forecasting

### 🤖 Advanced AI

Future AI functionality could include:

* Multilingual chatbot
* Crowd prediction
* Intelligent FAQ assistant
* Complaint classification
* Operational recommendations
* Peak-hour alerts

---

# 🛠️ Technology Stack

The project is designed as a modern full-stack application.

### Frontend

* React
* JavaScript/TypeScript
* HTML5
* CSS3
* Responsive UI
* QR Code generation

### Backend

* REST APIs
* Server-side business logic
* Booking management
* Rack allocation
* Footfall management

### Database

The system can store:

* Devotees
* Bookings
* Items
* Rack information
* Payments
* Footfall records
* Pickup records
* Staff information

### AI

* DivyaSeva AI Assistant
* Rule-based fallback
* English/Hindi support

### Future Integrations

* SMS gateway
* WhatsApp Business API
* Payment gateway
* Electronic locker hardware
* IoT controllers

---

# 📁 Suggested Project Structure

```text
DivyaCloak/
│
├── frontend/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── hooks/
│   └── assets/
│
├── backend/
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   ├── services/
│   └── middleware/
│
├── database/
│   ├── schema/
│   └── seed/
│
├── docs/
│   ├── architecture/
│   └── api/
│
├── .env.example
├── .gitignore
├── package.json
└── README.md
```

> Adjust this structure according to the actual structure of your repository.

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/DivyaCloak.git
```

Navigate into the project:

```bash
cd DivyaCloak
```

Install dependencies:

```bash
npm install
```

Create an environment file:

```bash
cp .env.example .env
```

Configure the required environment variables.

Start the development server:

```bash
npm run dev
```

---

# 🔑 Environment Variables

Example:

```env
DATABASE_URL=your_database_url
API_BASE_URL=your_api_url
AI_API_KEY=your_ai_api_key
PAYMENT_API_KEY=your_payment_api_key
SMS_API_KEY=your_sms_api_key
```

> Never commit real API keys, passwords, database credentials, or secrets to GitHub.

---

# 🧪 MVP Status

| Feature                 | Status     |
| ----------------------- | ---------- |
| Devotee Booking         | ✅ Complete |
| Item Pricing            | ✅ Complete |
| Digital QR Pass         | ✅ Complete |
| 4-Digit Security PIN    | ✅ Complete |
| Staff POS Kiosk         | ✅ Complete |
| 36-Rack Warehouse Map   | ✅ Complete |
| Footfall Counter        | ✅ Complete |
| 7-Day Analytics         | ✅ Complete |
| DivyaSeva Assistant     | ✅ Complete |
| Rule-Based AI Fallback  | ✅ Complete |
| SMS Notifications       | 🚧 Planned |
| WhatsApp Integration    | 🚧 Planned |
| One-Tap Pickup          | 🚧 Planned |
| Electronic Locker Relay | 🚧 Planned |
| Advanced AI Analytics   | 🔮 Future  |

---

# 🎯 Project Vision

DivyaCloak aims to modernize the traditional temple cloakroom experience by combining:

**Digital Booking + Secure Storage + QR Technology + Crowd Analytics + AI**

The long-term vision is to create a scalable platform that can be deployed across different temples and pilgrimage destinations in India.

Instead of relying entirely on manual token systems and physical queues, temples could use a centralized digital platform to manage belongings and understand visitor flow.

---

# 🌐 Potential Deployment

DivyaCloak can be adapted for:

* 🛕 Temples
* 🙏 Pilgrimage centers
* 🏛️ Religious sites
* 🎪 Large religious events
* 🚉 High-footfall visitor locations
* 🏟️ Other locations where temporary safe-keeping is required

Each location could have its own:

```text
Temple
 ├── Cloakrooms
 ├── Staff Accounts
 ├── Rack Configuration
 ├── Pricing
 ├── Footfall Data
 └── Analytics Dashboard
```

---

# 💡 Why DivyaCloak?

Traditional cloakrooms can involve:

❌ Long queues
❌ Manual token management
❌ Difficulty finding stored items
❌ Limited crowd visibility
❌ Manual record keeping

DivyaCloak introduces:

✅ Digital booking
✅ QR-based tokens
✅ Security PINs
✅ Rack management
✅ Real-time footfall tracking
✅ Crowd analytics
✅ Multilingual assistance

---

# 🤝 Contributing

Contributions are welcome.

If you would like to improve DivyaCloak:

1. Fork the repository
2. Create a new branch

```bash
git checkout -b feature/new-feature
```

3. Make your changes
4. Commit your changes

```bash
git commit -m "Add new feature"
```

5. Push the branch

```bash
git push origin feature/new-feature
```

6. Open a Pull Request

---

# 📜 License

This project is currently intended as an MVP/prototype.

Add your preferred open-source license here, such as MIT, before publishing the repository for external contributions.

---

# 👨‍💻 Author

**Manoranjan Kumar Jha**

Full-Stack Developer | Python | SQL | Power BI | Java

---

## ⭐ Support the Project

If you find **DivyaCloak** interesting or useful, consider giving the repository a ⭐ on GitHub.

**DivyaCloak — Making Temple Visits Safer, Simpler & Smarter. 🛕❤️**

---


Here is Simple of our site 
<img width="1919" height="905" alt="image" src="https://github.com/user-attachments/assets/18faa5e8-50f0-4d98-adaf-6126655187d5" />

<img width="1919" height="909" alt="image" src="https://github.com/user-attachments/assets/f7cc9196-726b-4f47-9fe7-d8a86ba0c36c" />

<img width="1914" height="905" alt="image" src="https://github.com/user-attachments/assets/90dfe9c0-ebe9-4b2f-b2d9-253b73baed9d" />
<img width="1919" height="901" alt="image" src="https://github.com/user-attachments/assets/882d7be5-710f-45eb-be41-41c8c666de97" />
<img width="1919" height="911" alt="image" src="https://github.com/user-attachments/assets/a2854785-e102-4fb9-b79d-1f5c990678c1" />

<img width="1604" height="702" alt="image" src="https://github.com/user-attachments/assets/a8b8c0be-891f-48e5-8226-7e59eb1042f7" />
<img width="1623" height="757" alt="image" src="https://github.com/user-attachments/assets/3e5cbc4b-2385-48ea-9624-ddc66c6ad8b3" />

<img width="1915" height="777" alt="image" src="https://github.com/user-attachments/assets/bd5d24ae-6c5e-45c2-b09b-fdc05d47fa55" />

<img width="1535" height="737" alt="Screenshot 2026-09-10 085748" src="https://github.com/user-attachments/assets/3737f554-8cfc-49c3-9428-e8f79154220b" />
<img width="1539" height="867" alt="image" src="https://github.com/user-attachments/assets/5e6a9419-7922-45de-ad2c-8bdfc0864774" />

<img width="1540" height="508" alt="image" src="https://github.com/user-attachments/assets/236d9af9-ede3-43d7-8835-ac1f64f213f4" />
<img width="1508" height="760" alt="Screenshot 2026-09-10 090044" src="https://github.com/user-attachments/assets/abb1384c-39e9-484d-8c06-398f85d53f9d" />
<img width="1521" height="650" alt="image" src="https://github.com/user-attachments/assets/44bb51e1-3f75-4a02-a3f6-a57f61f562d9" />

<img width="1545" height="246" alt="image" src="https://github.com/user-attachments/assets/0347ea1b-30f2-4b81-b161-e6e7eaaeb896" />
<img width="1392" height="778" alt="image" src="https://github.com/user-attachments/assets/e0217860-ab06-47ec-a8df-6e629988ecda" />
<img width="1390" height="364" alt="image" src="https://github.com/user-attachments/assets/08b4f45a-d041-4955-b84e-a40e48168db7" />
<img width="602" height="731" alt="image" src="https://github.com/user-attachments/assets/dac7f427-b0e5-4578-96e1-2d116b0c8d9f" />
<img width="625" height="729" alt="image" src="https://github.com/user-attachments/assets/fc2dc183-3eb4-4dbe-aeb2-a67653dd1c6c" />

<img width="597" height="726" alt="image" src="https://github.com/user-attachments/assets/13a17e90-ab89-48a7-b92a-80f054415896" />

<img width="230" height="41" alt="image" src="https://github.com/user-attachments/assets/7fe185f2-9915-44bb-884c-2882d87476e4" />
<img width="1393" height="848" alt="image" src="https://github.com/user-attachments/assets/ae3690bb-cf29-4fdd-adb5-575041f8f34f" />
<img width="1372" height="442" alt="image" src="https://github.com/user-attachments/assets/9c504b87-b9cb-4b86-84dd-2c84552bd974" />






