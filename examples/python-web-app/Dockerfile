# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the requirements.txt file into the container at /app
COPY requirements.txt .

# Install any needed packages specified in requirements.txt
RUN apt-get update \
    && apt-get install -y python3 python3-pip \
    && pip install --no-cache-dir -r requirements.txt

# Copy the rest of your application's code
COPY . .

# Set the working directory to where manage.py is located
WORKDIR /app/devops

ENTRYPOINT [ "python3" ]
# Define the command to run your application
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
