# JMeter API Chaining on Dmoney Portal

## 📘 Introduction

This project demonstrates **API chaining and performance testing** on the **Dmoney Portal** using **Apache JMeter**.  
The test plan (`dmoney.jmx`) simulates real-world financial transaction flows such as deposit, send money, and merchant payments using multiple concurrent users.

**Base URL:**  
https://dmoneyportal.roadtocareer.net/

---

## 📌 Test Scenario

From the Dmoney API collection, a JMeter test plan (`dmoney.jmx`) has been created to execute the following workflows:

### 🔹 1. Deposit  
- 5 agents perform deposits for 10 customers

### 🔹 2. Send Money  
- 5 customers send money to another 10 customers

### 🔹 3. Payment  
- 5 customers make payments to 2 merchants

---

## 🔄 API Chaining Design

The following rules are applied in this test plan:

- Login is performed once as **Admin** to generate a **token**  
- The generated token is used for all API requests  
- Three **Thread Groups** are created:
  - Deposit
  - Send Money
  - Payment  

- Three **CSV files** are used to manage test data:
  - `deposit.csv`
  - `sendMoney.csv`
  - `payment.csv`

- Transaction **amounts are dynamic** using **Random Variable Controller**
- Small amounts are used so account balances never become zero
- Each thread group has a **ramp-up time of 120 seconds**
- **Assertions** are added to ensure all transactions are successful

---

## 📁 Project Files

| File | Description |
|------|-------------|
| `dmoney.jmx` | JMeter test plan for API chaining |
| `deposit.csv` | Agent → Customer deposit data |
| `sendMoney.csv` | Customer → Customer transfer data |
| `payment.csv` | Customer → Merchant payment data |

---

## ⚙ Pre-Requisites

Before running this project, make sure you have:

- Java JDK (LTS version) installed  
- Apache JMeter installed  
- `JAVA_HOME` environment variable set  
- `JMETER_HOME` environment variable set  

---

## ▶ How to Run This Project

1. Clone this repository  
2. Install and configure Java and JMeter  
3. Open **Apache JMeter**  
4. Open the file `dmoney.jmx`  
5. Update the paths of:
   - `deposit.csv`
   - `sendMoney.csv`
   - `payment.csv`
6. Click **Start (▶)** to execute the test plan  
7. View results in:
   - Summary Report  
   - Aggregate Report  
   - View Results Tree  

---

## 📊 Result Analysis

The performance results can be analyzed using JMeter listeners such as:
- Summary Report
- Aggregate Report
- View Results Tree

These reports provide information about response time, throughput, and success/failure of API requests.

---

## 📌 Notes

This project demonstrates a complete **API chaining and transaction simulation** for a digital wallet system using Apache JMeter.  
It can be extended for **load testing, stress testing, and performance monitoring**.

