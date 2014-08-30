FROM        google/debian:wheezy
ADD         mariadb.sources.list /etc/apt/sources.list.d/mariadb.sources.list
RUN         apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 0xcbcb082a1bb943db
RUN         apt-get update -y && apt-get install -y -q mariadb-server
RUN         sed -i 's/^\(bind-address\s.*\)/# \1/' /etc/mysql/my.cnf && \
            echo "mysqld_safe &" > /tmp/config && \
            echo "mysqladmin --silent --wait=30 ping || exit 1" >> /tmp/config && \
            echo "mysql -e 'GRANT ALL PRIVILEGES ON *.* TO \"root\"@\"%\";'" >> /tmp/config && \
            bash /tmp/config && \
            rm -f /tmp/config
VOLUME      ["/data", "/etc/mysql", "/var/lib/mysql"]
WORKDIR     /data
CMD         ["mysqld_safe"]
EXPOSE      3306
