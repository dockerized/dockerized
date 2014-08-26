FROM        google/python:latest
WORKDIR     /shadowsocks
RUN         virtualenv /env
ADD         config.json /shadowsocks/config.json
ADD         requirements.txt /shadowsocks/requirements.txt
RUN         /env/bin/pip install requirements.txt
EXPOSE      10010

CMD         []
ENTRYPOINT  ["/env/bin/ssserver", "-c", "/shadowsocks/config.json"]
