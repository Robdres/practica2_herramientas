FROM python:3.10-slim

WORKDIR /app

RUN echo "Installing dependencies"
COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
RUN echo "Initializating App"

CMD ["python", "main.py"]

