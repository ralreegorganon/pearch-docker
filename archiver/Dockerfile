FROM ubuntu:14.04
MAINTAINER jasonedwardjones@gmail.com

RUN apt-get -y -q install postgresql-client-9.3 git golang build-essential

ENV HOME /root
ENV GOPATH /root/go
ENV PATH /root/go/bin:$PATH

RUN mkdir -p $GOPATH/src/github.com/ralreegorganon
RUN cd $GOPATH/src/github.com/ralreegorganon; git clone https://github.com/ralreegorganon/pearch.git; cd pearch; go get; go build
RUN go get bitbucket.org/liamstask/goose/cmd/goose

ENV PEARCH_HOME $GOPATH/src/github.com/ralreegorganon/pearch

ADD start /start
RUN chmod 0755 /start
CMD ["/start"]