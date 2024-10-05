FROM python:3.9-slim

# Definindo diretório de trabalho
WORKDIR /app


COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .


COPY wait-for-it.sh /usr/local/bin/wait-for-it.sh
RUN chmod +x /usr/local/bin/wait-for-it.sh


EXPOSE 5000


CMD ["wait-for-it.sh", "mysql:3306", "--", "flask", "run", "--host=0.0.0.0", "--port=5000"]

