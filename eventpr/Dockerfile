# Use official Python image
FROM python:3.10-slim

# Install system dependencies (distutils, gcc, etc.)
RUN apt-get update \
    && apt-get install -y python3-distutils gcc build-essential \
    && apt-get clean

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Set work directory
WORKDIR /app

# Install Python dependencies
COPY requirements.txt /app/
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy project
COPY . /app/

# Expose port
EXPOSE 8000

# Run Django app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
# Use official Python image
FROM python:3.10-slim


# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set working directory
WORKDIR /app

# Install dependencies
COPY requirements.txt /app/
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy project files
COPY . /app/

# Collect static files (if needed, optional)
# RUN python manage.py collectstatic --noinput

# Run migrations (if you want to auto-migrate; optional)
# RUN python manage.py migrate

# Expose port (Django default)
EXPOSE 8000

# Command to run Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]