FROM python:3.9.16-alpine3.18

LABEL maintainer=joe@twr.io

COPY ./Pipfile* /app/

WORKDIR /app

RUN apk add --update --no-cache bind-tools ca-certificates gcc musl-dev python3-dev libffi-dev openssl-dev

RUN pip install pipenv

RUN pipenv install --system --deploy

RUN apk del gcc musl-dev python3-dev libffi-dev openssl-dev

COPY ./magtape-init.py /app/

CMD ["python", "magtape-init.py"]
