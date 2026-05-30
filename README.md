# Weather Forecasting API System (Core Java & JDBC)

## 🌤️ Project Overview
This project serves as the backend communication and database routing layer for a Weather Forecasting Application. Built entirely using **Core Java**, the application exposes structured endpoints to handle location-based queries, implements secure database lookups via **Java Database Connectivity (JDBC)**, and extracts real-time climate metrics from a localized **MySQL database system**.

---

## 🔗 Live API Documentation
The comprehensive technical manual, query schemas, and fault-tolerance exception examples for this system have been fully mapped and published via Postman:

👉 **[View Live Postman API Documentation](https://documenter.getpostman.com/view/54958983/2sBXwntCCc)**

> **Note on Local Execution:** Clicking the live "Send" or "Try" buttons on the web-based Postman documentation will result in a browser-level Cloud Agent network isolation error. This is expected security behavior as the underlying compiled Java application and MySQL relational instances run strictly within a local host environment (`localhost:8000`). Verified request structures and exact JSON data returns are mapped under the document's response examples.

---

## 🛠️ Tech Stack & Core Architecture
* **Backend Runtime:** Core Java Development Kit (JDK)
* **Database Layer:** MySQL Relational Database Server
* **Connectivity Driver:** JDBC (Java Database Connectivity) Driver MySQL Connector/J
* **API Standardization & Schema Design:** Postman API Network

---

## 📊 Database Schema Map (MySQL)
The application interacts with a localized database table named `weather_records` containing the following primary key indexes and column definitions:

| Column Name | Data Type | Key Attribute | Description |
| :--- | :--- | :--- | :--- |
| `city` | `VARCHAR(100)` | **Primary Key** | The unique validated geographical location name. |
| `temperature` | `VARCHAR(10)` | | Climatological thermal metrics (e.g., 42°C). |
| `humidity` | `VARCHAR(10)` | | Relative ambient atmospheric moisture percentages. |
| `weather_condition` | `VARCHAR(50)` | | Core visual weather indicators (Sunny, Rainy, etc.). |

---

## 🚫 System Exception Architecture
The core Java logic utilizes strict conditional error boundaries to maintain runtime application stability:
* **Success Path (200 OK):** Triggered when the input query string explicitly matches an indexed row key within the MySQL table, outputting a complete parsed climate data package.
* **Fault Path (404 Not Found Exception):** Triggered when a non-existent or invalid city name string is passed. The JDBC catch block intercepts the missing index exception and safe-routes a structured error notification matrix back to the client interface instead of throwing an unhandled stack trace crash.
