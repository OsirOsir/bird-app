# Bird API

Bird API is a lightweight **Flask REST API** for storing and retrieving information about birds.

The project demonstrates backend development with Flask, RESTful routing, SQLAlchemy models, database migrations, environment-based configuration, and JSON API responses.

## Features

- RESTful API built with Flask
- Retrieve individual bird records by ID
- SQLAlchemy database models
- Database migrations using Flask-Migrate and Alembic
- Seed script for populating sample bird data
- JSON responses
- Environment-based database configuration
- PostgreSQL support

## Tech Stack

### Backend
- Python
- Flask
- Flask-RESTful

### Database
- PostgreSQL
- SQLAlchemy
- Flask-SQLAlchemy

### Database Management
- Flask-Migrate
- Alembic

### Serialization
- SQLAlchemy Serializer

## Project Structure

```text
bird-app/
├── app.py
├── models.py
├── seed.py
├── requirements.txt
└── migrations/
    ├── alembic.ini
    ├── env.py
    ├── script.py.mako
    └── versions/
        └── 22ef2678560b_create_table_birds.py
```

## Data Model

The application currently contains a `Bird` model with the following fields:

| Field | Type | Description |
|---|---|---|
| `id` | Integer | Unique identifier |
| `name` | String | Common name of the bird |
| `species` | String | Scientific species name |

Example record:

```json
{
  "id": 1,
  "name": "Black-Capped Chickadee",
  "species": "Poecile Atricapillus"
}
```

## API Endpoint

### Get a Bird by ID

```http
GET /birds/<id>
```

Example request:

```text
GET /birds/1
```

Example response:

```json
{
  "id": 1,
  "name": "Black-Capped Chickadee",
  "species": "Poecile Atricapillus"
}
```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/OsirOsir/bird-app.git
cd bird-app
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Linux/macOS:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Database Configuration

The application reads the database connection from the `DATABASE_URI` environment variable.

Example:

```env
DATABASE_URI=postgresql://username:password@localhost/bird_db
```

Do not commit actual passwords or database credentials to GitHub.

On Linux/macOS:

```bash
export DATABASE_URI="postgresql://username:password@localhost/bird_db"
```

On Windows PowerShell:

```powershell
$env:DATABASE_URI="postgresql://username:password@localhost/bird_db"
```

## Database Setup

Apply the existing database migrations:

```bash
flask db upgrade
```

This creates the `birds` table.

## Seed the Database

The project includes sample bird records.

Run:

```bash
python seed.py
```

The seed script adds sample birds including:

- Black-Capped Chickadee
- Grackle
- Common Starling
- Mourning Dove

## Run the Application

Start the Flask application with:

```bash
flask --app app run
```

Alternatively:

```bash
python app.py
```

## Example Usage

Once the API is running, retrieve a bird with:

```text
http://127.0.0.1:5000/birds/1
```

The server responds with the selected bird as JSON.

## Project Goals

This project demonstrates practical experience with:

- Python backend development
- Flask REST APIs
- RESTful routing
- Relational data modelling
- SQLAlchemy ORM
- PostgreSQL integration
- Database migrations
- Database seeding
- JSON serialization
- Environment-based application configuration
- Git and GitHub version control

## Future Improvements

Possible extensions include:

- Retrieve all birds
- Create new bird records
- Update existing records
- Delete bird records
- Search and filter birds
- Improved validation and error handling
- Automated API tests
- API documentation

## License

This project is intended for educational and portfolio purposes.
