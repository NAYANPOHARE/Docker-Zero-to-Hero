FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/

RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create virtual environment and install dependencies
RUN python3 -m venv venv1 && \
    venv1/bin/pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

# Run the application using python from the virtual environment
CMD venv1/bin/python3 manage.py runserver 0.0.0.0:8000
