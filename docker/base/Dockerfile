# OLD
# FROM kalilinux/kali-rolling

# NEW (lightweight and Railway-friendly)
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Install OS-level dependencies
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git curl wget build-essential python3-dev libffi-dev libssl-dev \
    tzdata && \
    rm -rf /var/lib/apt/lists/*

# Copy Agent Zero code
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt || cat /root/.pip/pip.log

# Expose default port and start app
EXPOSE 7860
CMD ["python", "main.py"]