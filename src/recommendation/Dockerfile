FROM python:3.9-slim AS base
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN  python3-pip install 
COPY . .
ENTRYPOINT [ "python","recommendation_server.py" ]
