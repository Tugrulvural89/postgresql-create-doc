# PostgreSQL Create Documentation

# Accessing PostgreSQL

# Access PostgreSQL with the default user. If you have a Docker container, use -h hostname -W pass with exec. For example: psql -U username -h hostname -W -d database. If you don't # have a user, use the PostgreSQL default user. If you don't have a database, use the default database postgres.

sudo -u postgres psql

# Create Database

CREATE DATABASE database;

# User Management

# If you don't have a user:

CREATE USER username WITH PASSWORD 'password';

# If you already have a user:

GRANT ALL PRIVILEGES ON DATABASE database TO username;

ALTER ROLE username SET client_encoding TO 'utf8';
ALTER ROLE username SET default_transaction_isolation TO 'read committed';
ALTER ROLE username SET timezone TO 'UTC';

# Quit PostgreSQL

\q

# Django Project Configuration

# Install psycopg with binary for Django projects

pip install "psycopg[binary,pool]"

# Install env pip

pip install load-dotenv

# Check pip link for documentation: https://pypi.org/project/python-dotenv/

# Create .env file in your project root

# Change settings.py in Django Project

# Configure your settings.py to use environment variables for database configuration.

# Update or Install Django Dependencies

pip install -r requirements.txt

# Make Migrations and Migrate on Project Root

python manage.py makemigrations
python manage.py migrate
