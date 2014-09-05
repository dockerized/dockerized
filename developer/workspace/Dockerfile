FROM        google/debian:wheezy
RUN         apt-get update -y
RUN         apt-get install --no-install-recommends -y -q curl build-essential ca-certificates git mercurial bzr python python-dev vim
RUN         mkdir -p /developer/workspace
WORKDIR     /developer
RUN         hg clone http://code.google.com/p/go
RUN         cd go && hg update release && cd src && ./make.bash --no-clean 2>&1
ENV         GOROOT /developer/go
ENV         GOPATH /developer/workspace
ENV         PATH /developer/go/bin:/developer/workspace/bin:$PATH
CMD         ["/bin/bash"]
