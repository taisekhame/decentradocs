# Use Python 3.10
FROM python:3.10-slim

# Install Rust (required for pysui-fastcrypto)
RUN apt-get update && apt-get install -y curl build-essential \
    && curl https://sh.rustup.rs -sSf | sh -s -- -y

ENV PATH="/root/.cargo/bin:${PATH}"

# Set work directory
WORKDIR /app

# Copy project
COPY . /app

# Upgrade pip & install requirements
RUN python -m pip install --upgrade pip
RUN pip install -r requirements.txt

# Expose backend port
EXPOSE 8000

# Run backend
CMD ["python", "run.py"]