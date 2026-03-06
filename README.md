# DBT E-Commerce Data Platform

A comprehensive data engineering project demonstrating an end-to-end ELT pipeline using **dbt (data build tool)**, **PostgreSQL**, and **Docker**. This project orchestrates a containerized environment to generate synthetic sales data, load it into a data warehouse, and perform analytical transformations.

## 🏗️ Architecture Overview

The project follows a modern data stack architecture:
1.  **Data Source**: A Python-based generator (`generate-sales.py`) that simulates e-commerce transactions.
2.  **Warehouse**: A PostgreSQL 15 instance serving as the centralized data warehouse.
3.  **Transformation Layer**: dbt Core handles the modular SQL transformations (Models, Tests, and Snapshots).
4.  **Orchestration**: Docker Compose manages the lifecycle of all services.

## 🚀 Getting Started

### Prerequisites
* [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running.
* [Git](https://git-scm.com/) for version control.

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/hassanin1971/dbt-ecommerce.git](https://github.com/hassanin1971/dbt-ecommerce.git)
    cd dbt-ecommerce
    ```

2.  **Environment Configuration:**
    Create a `.env` file in the root directory to store your credentials (do not commit this file to GitHub):
    ```env
    POSTGRES_USER=dbt_user
    POSTGRES_PASSWORD=dbt_password
    POSTGRES_DB=dbt_warehouse
    ```

3.  **Build and Start the Containers:**
    ```bash
    docker-compose up -d --build
    ```

## 📂 Project Structure

```text
DBT-ECOMMERCE/
├── data-source/           # Python scripts for synthetic data generation
├── dbt_project/           # Core dbt directory
│   ├── models/            # SQL transformation logic
│   ├── seeds/             # Static CSV data
│   ├── tests/             # Data quality assertions
│   └── dbt_project.yml    # dbt configuration file
├── docker-compose.yml     # Infrastructure orchestration
├── Dockerfile             # Custom dbt-core image definition
└── .gitignore             # Standard git exclusion rules