FROM python:3.9-slim-buster

LABEL Name="Python Flask Demo App" Version=2.2.2
LABEL org.opencontainers.image.source = "https://github.com/SaiSravani-39/python-demoapp-DS"

ARG srcDir=src
WORKDIR /app
COPY $srcDir/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY $srcDir/run.py .
COPY $srcDir/app ./app

EXPOSE 5000

CMD ["gunicorn", "-b", "0.0.0.0:5000", "run:app"]
