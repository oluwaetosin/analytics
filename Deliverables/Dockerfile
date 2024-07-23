FROM python:3.10-slim-buster

WORKDIR src

COPY ./requirements.txt requirements.txt

RUN apt update -y

RUN apt install build-essential libpq-dev -y

RUN pip install -r requirements.txt

COPY ./ .

CMD python app.py