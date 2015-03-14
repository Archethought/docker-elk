FROM ubuntu:14.04
MAINTAINER Peter Klipfel <peter@archethought.com>

ADD https://download.elasticsearch.org/kibana/kibana/kibana-4.0.1-linux-x64.tar.gz /tmp/

RUN ["tar", "-C", "/opt", "-xf", "/tmp/kibana-4.0.1-linux-x64.tar.gz"]
RUN ["rm", "-f", "/tmp/kibana-4.0.1-linux-x64.tar.gz"]

RUN mkdir /src
ADD run /src/run

RUN chown -R nobody:nogroup /opt/kibana-4.0.1-linux-x64

USER nobody

CMD ["/src/run"]

EXPOSE 8080

