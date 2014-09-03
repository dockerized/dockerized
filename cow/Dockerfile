FROM        google/golang:latest
RUN         go get -u github.com/cyfdecyf/cow
RUN         mkdir .cow
COPY        rc .cow/rc
EXPOSE      10000
CMD         ["cow"]
