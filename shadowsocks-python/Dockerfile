FROM        google/python:latest
RUN         mkdir /shadowsocks
RUN         apt-get install --no-install-recommends -y -q swig
RUN         virtualenv /env
ADD         config.json /shadowsocks/config.json
ADD         requirements.txt /shadowsocks/requirements.txt
RUN         /env/bin/pip install -r /shadowsocks/requirements.txt
EXPOSE      10086

ENTRYPOINT  ["/env/bin/ssserver", "-c", "/shadowsocks/config.json"]
