FROM        google/golang:latest
RUN         go get -u github.com/shadowsocks/shadowsocks-go/cmd/shadowsocks-server
COPY        config.json .
EXPOSE      10010
CMD         ["shadowsocks-server"]
