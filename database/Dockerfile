FROM ubuntu:14.04
MAINTAINER jasonedwardjones@gmail.com

RUN apt-get -y -q install postgresql-9.3 postgresql-client-9.3 postgresql-contrib-9.3

EXPOSE 5432

RUN echo "host all  all    0.0.0.0/0  md5" >> /etc/postgresql/9.3/main/pg_hba.conf
RUN echo "listen_addresses='*'" >> /etc/postgresql/9.3/main/postgresql.conf

ADD start /start
RUN chmod 0755 /start

CMD ["/start"]