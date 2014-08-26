FROM        google/python:latest
RUN         virtualenv /env
COPY        config.json .
COPY        requirements.txt .
RUN         /env/bin/pip install requirements.txt
EXPOSE      10010

CMD         ["/env/bin/ssserver", "-c", "config.json"]
