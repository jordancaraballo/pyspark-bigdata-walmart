FROM python:3.11-slim

RUN apt-get update && apt-get install -y \
    openjdk-21-jdk \
    && rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
ENV PATH="${JAVA_HOME}/bin:${PATH}"

WORKDIR /app

RUN pip install --no-cache-dir \
    pyspark \
    pandas \
    numpy

COPY . .

CMD ["python"]