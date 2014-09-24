FROM        ubuntu:14.04
RUN         apt-get update -y
RUN         apt-get install --no-install-recommends -y -q curl build-essential ca-certificates git mercurial bzr python python-dev vim curl wget
RUN         useradd developer
RUN         mkdir -p /home/developer/workspace
WORKDIR     /home/developer

# CONFIG
ADD         vim .vim
ADD         vimrc .vimrc
ADD         vimrc.bundles .vimrc.bundles
ADD         gitconfig /home/developer/.gitconfig

# Golang
RUN         hg clone http://code.google.com/p/go
RUN         cd go && hg update release && cd src && ./make.bash --no-clean 2>&1

# Env
ENV         HOME /home/developer
ENV         GOROOT /home/developer/go
ENV         GOPATH /home/developer/workspace
ENV         PATH /home/developer/go/bin:/home/developer/workspace/bin:$PATH

# Shared data volume
RUN         mkdir /var/shared/
RUN         chown -R developer:developer /var/shared
VOLUME      /var/shared

# Switch user
RUN         chown -R developer:developer /home/developer
USER        developer
