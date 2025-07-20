FROM python:3.9-slim AS base
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN pip install --upgrade pip
RUN  pip install -r requirements.txt
COPY . .
CMD [ "python","recommendation_server.py" ]
