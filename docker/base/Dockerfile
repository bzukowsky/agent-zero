# Use a slim, production-grade Python image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Install OS-level dependencies
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git curl wget build-essential libffi-dev libssl-dev tzdata ffmpeg && \
    rm -rf /var/lib/apt/lists/*

# Copy only needed files from your fork
COPY . .

# Install Python dependencies
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# Expose expected port
EXPOSE 7860

# Replace this with the actual launch script or module
CMD ["python", "agent_zero/app.py"]
