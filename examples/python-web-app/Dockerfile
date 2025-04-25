FROM ubuntu

WORKDIR /app

# Copy requirements and app folder into the container
COPY requirements.txt /app/
COPY devops /app/

# Install necessary packages
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create and install dependencies in a virtual environment
RUN python3 -m venv venv1 && \
    venv1/bin/pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

# Command to run the app using the virtual environment
CMD ["venv1/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]
