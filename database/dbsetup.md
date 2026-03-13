# Database Setup Guide

This guide explains how to set up and run the MySQL database for this project using Docker Compose.

## Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed
- [Docker Compose](https://docs.docker.com/compose/) (included with Docker Desktop)

## Files Overview
- `docker-compose.yaml`: Defines the MySQL service, volumes, network, and health check.
- `.env`: Stores sensitive MySQL credentials and configuration variables.
- `initdb/`: Place any SQL scripts here to initialize the database automatically on first run.

## Steps

### 1. Configure Environment Variables
Edit the `.env` file in the `database/` folder to set your database name, user, and passwords:

```
MYSQL_DATABASE=IS436
MYSQL_USER=user
MYSQL_PASSWORD=your_secure_password
MYSQL_ROOT_PASSWORD=your_secure_root_password
```

### 2. (Optional) Add Initialization Scripts
Place any `.sql` files you want to run on first startup in the `initdb/` directory. These scripts will be executed automatically by MySQL.

### 3. Start the Database
Open a terminal in the `database/` directory and run:

```
docker compose up -d --build
```

- This will build and start the MySQL container in the background.
- The database will be accessible on port 3307 of your host machine.

### 4. Check Database Health
Docker Compose includes a health check for MySQL. To see the health status:

```
docker ps
```
- Look for the `STATUS` column. If it says `(healthy)`, the database is ready.
- If it says `(unhealthy)`, check your configuration or logs.

To see detailed health check logs:
```
docker inspect --format='{{json .State.Health}}' mysql-IS436
```

### 5. Stopping and Removing the Database
To stop the database:
```
docker compose down
```
This will stop and remove the container, but your data will persist in the `db_data` volume.

### 6. Resetting the Database
To remove all data and start fresh:
```
docker compose down -v
```
This will delete the container and the persistent data volume.

## Notes
- The database data is stored in a Docker volume named `db_data` for persistence.
- The health check ensures the database is running and ready before other services connect.
- Never commit your real passwords to version control. The `.env` file should be in `.gitignore`.

---
