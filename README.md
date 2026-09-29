# Jiran: AI-Assisted Inventory Optimization & Retailer Marketplace

**Small Stores. Big Network.**

Jiran is an AI-assisted inventory intelligence platform designed for small and mid-sized retailers. It helps retailers monitor inventory, identify stock imbalances, forecast demand, and facilitate the redistribution of excess inventory between stores.

The platform combines inventory management, analytics, stock classification, recommendations, alerts, and a retailer-to-retailer marketplace into a single system.

Jiran was developed as a **CSIT321 capstone project** by Team OSCORP at the **University of Wollongong in Dubai**.

---

## Overview

Small and mid-sized retailers often rely on spreadsheets, POS systems, and manual processes to manage inventory. This can result in excess or dead stock at one location while another location experiences shortages of the same products.

Jiran provides a centralized platform for:

* Inventory management
* Stock health monitoring
* Demand forecasting
* AI-assisted inventory recommendations
* Low-stock and inventory imbalance alerts
* Retailer-to-retailer stock redistribution

The objective is to improve inventory visibility and support data-driven decisions regarding stock movement between participating retailers.

---

## Key Features

### Inventory Management

Manage inventory across stores, products, and categories through manual updates and structured data imports.

### AI-Assisted Analytics

Analyze historical sales and inventory data to support demand forecasting, stock classification, and inventory optimization.

### Retailer Marketplace

Allow retailers to list excess inventory and request products from other participating retailers.

### Stock Health Monitoring

Classify inventory into **Low, Optimum, Excess, Slow, and Dead** categories to identify potential stock issues.

### Inventory Recommendations

Generate transfer and restocking recommendations based on inventory status, demand patterns, and stock imbalances.

### POS Integration

Prototype integration with **Square POS** for inventory and sales data workflows.

---

## AI / ML Components

Jiran uses machine learning and analytics to support inventory decision-making.

The system includes:

* Demand forecasting
* Stock classification
* Inventory transfer recommendations
* Restocking recommendations
* Feature importance analysis

### Stock Classification

| Status      | Meaning               | Example Action                |
| ----------- | --------------------- | ----------------------------- |
| **Low**     | Running low           | Restock or receive a transfer |
| **Optimum** | Healthy stock level   | No action required            |
| **Excess**  | Overstocked           | Transfer to another store     |
| **Slow**    | Slow-moving inventory | Consider redistribution       |
| **Dead**    | No recent sales       | Clear or redistribute         |

---

## Technology Stack

| Layer                    | Technologies                                       |
| ------------------------ | -------------------------------------------------- |
| **Frontend**             | React, Vite, JavaScript                            |
| **Backend / ML Service** | Python, FastAPI                                    |
| **Database**             | PostgreSQL, Supabase                               |
| **Authentication**       | Supabase Authentication                            |
| **Realtime**             | Supabase Realtime                                  |
| **Machine Learning**     | Prophet, XGBoost, Gradient Boosting, Random Forest |
| **Integration**          | Square POS                                         |
| **Version Control**      | Git, GitHub                                        |

---

## Project Structure

```text
Jiran/
├── start.sh
├── README.md
├── frontend/
│   ├── src/
│   ├── package.json
│   └── .env.example
└── ml_backend/
    ├── app.py
    ├── supabase_watcher.py
    ├── train.py
    ├── saved_models/
    ├── requirements.txt
    └── .env.example
```

---

## Getting Started

### Prerequisites

* Python 3.9+
* Node.js 18+
* A Supabase project

### 1. Clone the Repository

```bash
git clone https://github.com/harklook/Jiran.git
cd Jiran
```

### 2. Configure Environment Variables

Copy the example environment files:

```bash
cp frontend/.env.example frontend/.env
cp ml_backend/.env.example ml_backend/.env
```

Configure the required Supabase and API values in the respective `.env` files.

> **Security:** Never commit real API keys, credentials, access tokens, or Supabase service-role keys to version control.

### 3. Start the Application

```bash
./start.sh
```

The application runs the following services:

* **Frontend:** `http://localhost:5173`
* **ML Backend:** `http://localhost:8001`
* **API Documentation:** `http://localhost:8001/docs`

---

## ML API

| Method | Endpoint              | Description                        |
| ------ | --------------------- | ---------------------------------- |
| `GET`  | `/`                   | Health check                       |
| `POST` | `/predict-stock`      | Predict stock status               |
| `POST` | `/recommend`          | Generate inventory recommendations |
| `GET`  | `/feature-importance` | Return model feature importance    |

---

## Project Status and Limitations

Jiran is an **academic capstone prototype** and is not intended to serve as a production ERP system.

Current limitations include:

* Prototype-level POS integration
* Simplified workflows for academic demonstration
* No full payment gateway
* No mobile application
* Prototype and demonstration data used in some scenarios
* Regional focus on UAE/GCC retail use cases

The project demonstrates how inventory intelligence, demand forecasting, and retailer-to-retailer stock redistribution can be combined within a lightweight platform for small and mid-sized retailers.
