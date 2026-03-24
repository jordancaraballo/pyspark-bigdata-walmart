# Base image
FROM python:3.11-slim

# Install Java (required for PySpark)
RUN apt-get update && apt-get install -y \
    openjdk-26-jdk \
    && rm -rf /var/lib/apt/lists/*

# Set JAVA_HOME (important for Spark)
ENV JAVA_HOME=/usr/lib/jvm/java-26-openjdk-amd64
ENV PATH="$JAVA_HOME/bin:$PATH"

# Set working directory
WORKDIR /app

# Install Python dependencies
RUN pip install --no-cache-dir \
    pyspark \
    pandas \
    numpy

# Copy your code (optional)
COPY . .

# Default command (override as needed)
CMD ["python"]