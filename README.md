# Django-Todolist

A task management application (Todo List) built with Django. This project is designed to demonstrate skills in working with Django, Docker, and Docker Compose for portfolio purposes.

## Architecture

The project uses:
- **Docker** - for containerizing the Django application
- **MySQL** - as the database in a separate Docker container
- **Docker Compose** - for orchestrating the multi-container application

## Running Locally

### Prerequisites

Make sure you have installed:
- Docker

### Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/Bondaliname/dockerization_todolist.git
cd dockerization_todolist
```

2. Start the application using Docker Compose:
```bash
docker-compose --env-file .env.example up --build
```

### Verifying the Application

1. Open your browser and navigate to:
```
http://localhost:8000
```

2. Check container status:
```bash
docker-compose ps
```

3. View logs:
```bash
docker-compose logs -f
```

4. Verify database connection:
```bash
docker-compose exec web python manage.py showmigrations
```

### Cleanup

To stop and remove all containers, networks, and volumes:
```bash
# Stop containers
docker-compose down

# Remove containers along with volumes (database data)
docker-compose down -v

# Remove images as well
docker-compose down -v --rmi all

# Complete cleanup (including unused resources)
docker system prune -a --volumes
```

## Configuration

The project includes a `.env.example` file with sample environment settings.

You can create your own `.env` file based on `.env.example` to customize the settings.
