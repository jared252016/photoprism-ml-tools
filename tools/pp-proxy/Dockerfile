FROM python:3.8

RUN pip3 install pipenv
RUN pip3 install websockets
RUN pip3 install asyncio

ENV PROJECT_DIR /app

WORKDIR ${PROJECT_DIR}

COPY pp-proxy .
COPY . .

RUN pipenv install --deploy --ignore-pipfile

CMD ["pipenv", "run", "python", "pp-proxy", "start"]