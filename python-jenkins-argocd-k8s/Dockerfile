FROM python:3.10-slim

# Install distutils and other essential tools
RUN apt-get update && apt-get install -y python3-distutils gcc

# Set working directory
WORKDIR /app

# Copy files to container
COPY . .

# Upgrade pip and install Django
RUN pip install --upgrade pip
RUN pip install django==3.2

# Run migrations
RUN python manage.py migrate

# Expose port and run the server
EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
