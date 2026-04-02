# E-Waste Management System

**Author**: Akshita

A comprehensive full-stack web platform developed to streamline the collection, tracking, and recycling of electronic waste. The system enables users to request e-waste pickups while allowing administrators to manage, monitor, and process collection activities efficiently. It ensures proper handling and environmentally responsible disposal of electronic products through a structured digital workflow.

## 🛠️ Technology Stack
*   **Frontend**: React.js, Bootstrap
*   **Backend**: Java (Spring Boot)
*   **Database**: MySQL
*   **Tools**: Postman

---

## 🚀 Prerequisites
Before running the project, ensure you have the following installed:
1.  **Java JDK 17+** (Required for Spring Boot)
2.  **Node.js & NPM** (Required for React)
3.  **MySQL Server** (Running on port 3306)

---

## ⚙️ Setup & Installation

### 1. Database Setup
1.  Open MySQL Workbench or Command Line.
2.  Create a new database named `ewaste_management_system` (Specific to this project).
    ```sql
    CREATE DATABASE ewaste_management_system;
    ```
3.  **Important**: Configure your MySQL username and password in `E-WASTE-MGNT-BACKEND/E-Waste Management/src/main/resources/application.properties`.

### 2. Backend Setup (Spring Boot)
1.  Navigate to the backend folder:
    ```bash
    cd "E-WASTE-MGNT-BACKEND/E-Waste Management"
    ```
2.  **Configure Email** (Required for OTPs):
    *   Open `src/main/resources/application.properties`.
    *   Update `spring.mail.username` with your **Gmail**.
    *   Update `spring.mail.password` with your **Google App Password** (Not your login password. Search "App Passwords" in Google Account settings).
3.  Run the application:
    ```bash
    mvnw spring-boot:run
    ```
    *   The backend server will start on `http://localhost:8080`.

### 3. Frontend Setup (React)
1.  Navigate to the frontend folder:
    ```bash
    cd "E-WASTE-MGNT-FRONTEND/E-Waste"
    ```
2.  Install dependencies (first time only):
    ```bash
    npm install
    ```
3.  Start the application:
    ```bash
    npm start
    ```
    *   The frontend app will open at `http://localhost:3000`.

---

## 🧪 Modules & Features

### User Module
*   **Register/Login**: Secure access with OTP verification.
*   **Dashboard**: View profile, history, and status.
*   **Request Donation**: Submit details for e-waste pick-up.
*   **Profile Management**: Update personal details.

### Admin Module
*   **Dashboard**: Overview of all system activities.
*   **Manage Users**: View and manage registered users.
*   **Manage Donations**: View pending and completed donation requests.

---

## 🧪 How to Test (Step-by-Step)

### A. Register & Logic
1.  Go to `http://localhost:3000/register`.
2.  Fill in details and click **Register**.
3.  **Check your Email** (or Backend Console) for the **OTP**.
4.  Enter the OTP and click **Verify**.

### B. Forgot Password (OTP Flow)
1.  Go to Login -> **Forgot Password**.
2.  Enter Email -> **Send OTP**.
3.  Verify OTP -> Set New Password.

---

## 📡 API Testing (Postman)
If you prefer testing APIs directly:

1.  **Login**: `POST http://localhost:8080/login`
    *   Body: `{"email": "...", "password": "..."}`
    *   **Copy the Token** from response.
2.  **Get Details**: `GET http://localhost:8080/me`
    *   Header: `Authorization: Bearer <YOUR_TOKEN>`
3.  **Verify OTP**: `POST http://localhost:8080/verify-otp`
    *   Body: `{"email": "...", "otp": "..."}`

---

## ⚠️ Troubleshooting
*   **Backend won't start?** Check if port 8080 is free.
*   **Email not sending?** Verify your Google App Password is correct in `application.properties`.
*   **"Update Failed"?** Ensure you are sending the `Authorization: Bearer <token>` header in requests.
