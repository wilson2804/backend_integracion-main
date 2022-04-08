FROM alpine:3.10

RUN apk add --no-cache python3-dev \
    && pip3 install --upgrade pip

RUN apk add --update mysqlclient     

WORKDIR /apipython

COPY . /apipython

RUN pip3 --no-cache-dir install -r requirements.txt

RUN python3 manage.py makemigrations

RUN python3 manage.py migrate

CMD [ "python3", "manage.py runserver" ]