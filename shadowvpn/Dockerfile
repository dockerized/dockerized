FROM alpine
MAINTAINER Tian <xiocode@gmail.com>

RUN apk add -U autoconf \
               automake \
               build-base \
               gawk \
               git \
               iptables \
               libtool \
               linux-headers \
    && git clone --recursive https://github.com/clowwindy/ShadowVPN.git \
    && cd ShadowVPN \
    && ./autogen.sh \
    && ./configure --enable-static --sysconfdir=/etc \
    && make install \
    && cd .. \
    && rm -rf ShadowVPN \
    && apk del autoconf \
               automake \
               build-base \
               gawk \
               git \
               libtool \
               linux-headers

RUN sed -r -i "s/(password)=(.*)/\1=299792458/g" \
              /etc/shadowvpn/server.conf

EXPOSE 1123/udp

CMD shadowvpn -c /etc/shadowvpn/server.conf
