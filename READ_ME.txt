# PostgreSQL Python Flask API Project

A Flask-based web application with PostgreSQL database integration, featuring CRUD operations, stored procedures, and a web interface.

## 📋 Prerequisites

Before setting up this project, ensure you have the following installed:

- **Python 3.8 or higher**
- **PostgreSQL Database Server**
- **Git** (for cloning the repository)
- **pip** (Python package installer)

## 🚀 Getting Started

### Step 1: Clone the Repository

Open your terminal/command prompt and run:

```bash
git clone https://github.com/NiharDhimmar/ECommerceAPI.git
cd ECommerceAPI
```

### Step 2: Set Up Virtual Environment (Recommended)

Create and activate a virtual environment:

**On Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**On macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

Install all required packages:

```bash
pip install -r requirements.txt
```

### Step 4: Configure PostgreSQL Database

1. **Install PostgreSQL** if not already installed
   - Download from: https://www.postgresql.org/download/
   - Or use package manager: `sudo apt-get install postgresql` (Ubuntu/Debian)

2. **Create Database and User:**
   ```sql
   CREATE DATABASE "AgenticAI";
   CREATE USER postgres WITH PASSWORD 'eonian';
   GRANT ALL PRIVILEGES ON DATABASE "AgenticAI" TO postgres;
   ```

3. **Update Database Configuration** (if needed):
   Edit `app.py` and modify these lines:
   ```python
   DB_NAME = "AgenticAI"
   DB_USER = "postgres"
   DB_PASSWORD = "eonian"
   DB_HOST = "localhost"
   DB_PORT = "5433"  # Default is 5432
   ```

### Step 5: Run the Application

**Method 1: Direct Python Execution**
```bash
python app.py
```

**Method 2: Using Flask Development Server**
```bash
flask run
```

**Method 3: Using Python Module**
```bash
python -m flask run
```

### Step 6: Access the Application

Open your web browser and navigate to:
- **Main Application:** http://127.0.0.1:5000/ or http://localhost:5000/
- **API Endpoints:** Available at http://127.0.0.1:5000/api/

## 🛠️ Project Structure

```
ECommerceAPI/
├── app.py              # Main Flask application
├── requirements.txt     # Python dependencies
├── READ_ME.txt         # This file
├── templates/
│   └── index.html      # Web interface template
└── web.config          # Web server configuration
```

## 📡 API Endpoints

The application provides the following API endpoints:

- `GET /api/connect` - Test database connection
- `POST /api/create_table` - Create database tables and stored procedures
- `POST /api/insert_sample_data` - Insert sample data
- `POST /api/insert_user` - Insert new user
- `GET /api/fetch_data` - Fetch all users
- `POST /api/add_admin` - Add new admin
- `POST /api/update_admin` - Update existing admin
- `GET /api/fetch_admins` - Fetch all admins

## 🗄️ Database Schema

### Users Table
- `id` (SERIAL PRIMARY KEY)
- `name` (VARCHAR(100))
- `email` (VARCHAR(100) UNIQUE)

### Admin Table
- `Id` (SERIAL PRIMARY KEY)
- `ClientId` (UUID NOT NULL)
- `UserName` (TEXT UNIQUE NOT NULL)
- `Password` (TEXT NOT NULL)
- `Name` (TEXT NOT NULL)
- `Created` (TIMESTAMP WITH TIME ZONE NOT NULL)
- `Updated` (TIMESTAMP WITH TIME ZONE NOT NULL)

## 🔧 Troubleshooting

### Common Issues:

1. **Database Connection Failed:**
   - Ensure PostgreSQL is running
   - Check database credentials in `app.py`
   - Verify database exists

2. **Port Already in Use:**
   - Change port in `app.py` or kill existing process
   - Use: `flask run --port 5001`

3. **Module Not Found Errors:**
   - Activate virtual environment
   - Run: `pip install -r requirements.txt`

4. **Permission Denied:**
   - Run terminal as administrator (Windows)
   - Use `sudo` (Linux/macOS)

## 📝 Development

### Running in Development Mode:
```bash
export FLASK_ENV=development  # Linux/macOS
set FLASK_ENV=development     # Windows
flask run
```

### Debug Mode:
```bash
export FLASK_DEBUG=1  # Linux/macOS
set FLASK_DEBUG=1     # Windows
flask run
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -m 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit a pull request

## 📄 License

This project is open source and available under the MIT License.

---

**Note:** Make sure to keep your database credentials secure and never commit sensitive information to version control.