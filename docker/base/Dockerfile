# OLD
# FROM kalilinux/kali-rolling

# NEW (lightweight and Railway-friendly)
FROM python:3.10-slim

# Set working directory
WORKDIR /app

# Install OS-level dependencies
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git curl wget tzdata && \
    rm -rf /var/lib/apt/lists/*

# Copy Agent Zero code
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose default port and start app
EXPOSE 7860
CMD ["python", "main.py"]