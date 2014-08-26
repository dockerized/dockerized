FROM        google/python:latest
WORKDIR     /shadowsocks
RUN         virtualenv /env
ADD         config.json /shadowsocks/config.json
ADD         requirements.txt /shadowsocks/requirements.txt
RUN         /env/bin/pip install -r requirements.txt
EXPOSE      10086

CMD         []
ENTRYPOINT  ["/env/bin/ssserver", "-c", "/shadowsocks/config.json"]
