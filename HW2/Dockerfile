# Use an explicit base image tag
FROM python:3.12.2-slim

# Set the working directory
WORKDIR /app

# Install Poetry
RUN pip install 'poetry==1.8.2'

# Copy dependency files
COPY pyproject.toml poetry.lock ./

# Install dependencies
RUN poetry install

# Copy the rest of your code
COPY . .

# Specify the default command
ENTRYPOINT ["python", "main.py"]