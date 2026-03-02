FROM python:3.12

RUN apt-get update && apt-get install -y nano

WORKDIR /syxtrade

COPY src/syxtrade/ .
COPY src/syxtrade-modules/ ./modules/

RUN pip install -r requirements.txt
# RUN mv config/config.sample.json config/config.json

CMD ["python", "run.py"]