FROM        google/python:latest
RUN         RUN virtualenv /env
ADD         config.json .
ADD         requirements.txt .
RUN         /env/bin/pip install requirements.txt
EXPOSE      10010

CMD         ["/env/bin/ssserver", "-c", "config.json"]
