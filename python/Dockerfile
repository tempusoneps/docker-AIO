FROM python:3.12

RUN apt-get update && apt-get install -y nano

WORKDIR /syxtrade

COPY src/syxtrade/ .
COPY env/python/.env .
COPY src/syxtrade-modules/ ./modules/

RUN pip install --upgrade pip setuptools wheel

RUN pip install -r requirements.txt

CMD ["python", "run.py"]