FROM ubuntu:14.04
MAINTAINER Peter Klipfel <peter@archethought.com>

RUN ["apt-get", "install", "-y", "python-twisted", "tar"]
ADD https://download.elasticsearch.org/kibana/kibana/kibana-3.1.0.tar.gz /tmp/

RUN ["mkdir", "-p", "/var/www/"]
RUN ["tar", "-C", "/var/www", "-xf", "/tmp/kibana-3.1.0.tar.gz"]
RUN ["cp", "/var/www/kibana-3.1.0/app/dashboards/logstash.json", "/var/www/kibana-3.1.0/app/dashboards/default.json"]
RUN ["rm", "-f", "/tmp/kibana-3.1.0.tar.gz"]

USER nobody
WORKDIR /tmp
CMD ["/usr/bin/twistd", "-n", "web", "--path", "/var/www/kibana-3.1.0"]

EXPOSE 8080

