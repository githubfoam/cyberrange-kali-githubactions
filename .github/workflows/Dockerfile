# Base image
FROM python:3.11-slim

LABEL maintainer="you@example.com"
LABEL description="Shuffle - Open source SOAR backend"

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git curl build-essential libffi-dev libssl-dev \
    && rm -rf /var/lib/apt/lists/*

# Set workdir
WORKDIR /app

# Clone Shuffle repository
RUN git clone https://github.com/Shuffle/Shuffle.git /app

# Install backend Python dependencies
WORKDIR /app/backend
RUN pip install --no-cache-dir -r requirements.txt

# Shuffle backend port
EXPOSE 3001

# Environment variables
ENV PYTHONUNBUFFERED=1 \
    FLASK_ENV=production \
    SHUFFLE_APP_SECRET="shuffle-secret"

# Run backend
CMD ["python3", "app.py"]
