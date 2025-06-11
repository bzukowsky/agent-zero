FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Install OS-level dependencies
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git curl wget build-essential libffi-dev libssl-dev tzdata ffmpeg && \
    rm -rf /var/lib/apt/lists/*

# Copy your code
COPY . .

# Install Python dependencies
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# Let Railway know which port to expose
EXPOSE 7860

# Run the UI (modify port if needed)
CMD ["python", "run_ui.py"]
