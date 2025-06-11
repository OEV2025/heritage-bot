# Base image
FROM python:3.10-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    curl \
    && apt-get clean

# Set work directory
WORKDIR /app

# Copy project files into image
COPY . /app

# Install Python dependencies
RUN pip install --no-cache-dir rasa==3.6.11

# Install custom action dependencies (if needed)
RUN pip install -r requirements.txt || true

# Expose Rasa port
EXPOSE 5005

# Start Rasa server
CMD ["rasa", "run", "--enable-api", "--cors", "*", "--debug"]
