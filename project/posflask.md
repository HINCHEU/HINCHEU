# POS_flask Project Documentation

## 1. Overview
**POS_flask** is a Point of Sale (POS) system built using a modern web stack. It features a backend powered by **Python (Flask)** and a frontend enriched with **Vue.js** and **Bootstrap** for an interactive and responsive user experience. Additionally, the system integrates a **Telegram Bot** for notifications or remote commands.

## 2. Technology Stack
- **Backend Framework**: Python 3, Flask (v3.0.3)
- **Frontend Framework**: Vue.js, Bootstrap (via HTML templates and static files)
- **Database**: SQLite (managed via `database.db` and initialized with `db_init.py`)
- **Key Python Libraries**: 
  - `Jinja2` (Templating engine)
  - `requests` (For external API/Telegram integrations)
  - `pillow` (Image processing)
  - `Werkzeug` (WSGI web application library)

## 3. Project Structure
The repository follows a modular Flask application structure:

```text
D:\Web\POS_flask
├── README.md               # Project overview and run instructions
├── requirements.txt        # Python dependencies
├── app.py                  # Main Flask application entry point
├── database.db             # SQLite database file
├── db_init.py              # Database initialization and migration script
├── routes/                 # Flask Blueprints for handling requests
│   ├── category.py         # Category management logic
│   ├── dashboard.py        # Dashboard data and analytics
│   ├── product.py          # Product inventory management
│   ├── sale.py             # Sales records and history
│   ├── sell.py             # Active selling (cart/checkout) logic
│   ├── user.py             # User authentication and management
│   ├── utils.py            # Shared utility functions
│   └── __init__.py         
├── templates/              # Jinja2 HTML templates
│   ├── admin/              # Admin-facing UI components
│   └── user/               # Standard user/cashier UI components
└── static/                 # Static assets (CSS, JS, Vue components, Images)
```

## 4. Key Features / Modules
Based on the routing structure, the POS system includes the following core modules:

- **Dashboard**: Provides an overview of business performance, recent sales, and inventory alerts.
- **Product Management**: Allows users to add, edit, or remove products. Likely handles image uploads using `pillow`.
- **Category Management**: Grouping products into structured categories.
- **Selling Interface (POS)**: The active interface for cashiers to process transactions, likely utilizing Vue.js for dynamic, real-time cart updates without page reloads.
- **Sales History**: Viewing past transactions and generating receipts.
- **User Management**: Role-based access control (Admin vs. User), authentication, and account handling.
- **Telegram Integration**: Leverages the Telegram Bot API (via `requests`) to send alerts (e.g., end-of-day reports, large transactions, or stock warnings).

## 5. Setup & Installation
### Prerequisites
- Python 3.x installed
- Virtual Environment (recommended)

### Steps
1. **Clone/Navigate to the project directory:**
   ```bash
   cd D:\Web\POS_flask
   ```
2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```
3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Initialize the Database:**
   Run the initialization script to migrate and seed the database.
   ```bash
   python db_init.py
   ```
5. **Run the Application:**
   Start the Flask development server.
   ```bash
   python app.py
   ```
   The application will be accessible by default at `http://127.0.0.1:5000/`.
