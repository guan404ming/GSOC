FROM python:3.9-slim

WORKDIR /app

# Intentionally wrong file name to cause build failure
COPY requirements.txt.wrong .
RUN pip install --no-cache-dir -r requirements.txt.wrong

# Intentionally wrong file name to cause build failure
COPY app.py.wrong .

# Intentionally wrong command to cause runtime failure
CMD ["python", "wrong_app.py"] 