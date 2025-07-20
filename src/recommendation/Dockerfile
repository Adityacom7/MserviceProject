FROM python:3.9-slim AS base
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN apt install python3-pip
COPY . .
ENTRYPOINT [ "python","recommendation_server.py" ]
