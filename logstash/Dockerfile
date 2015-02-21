FROM java:7-jre
MAINTAINER Peter Klipfel <peter@archethought.com>

RUN apt-get update && apt-get install -y build-essential python-dev

RUN cd /tmp && \
    wget https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.tar.gz && \
    tar -xzvf ./logstash-1.4.2.tar.gz && \
    mv ./logstash-1.4.2 /opt/logstash && \
    rm ./logstash-1.4.2.tar.gz

RUN /opt/logstash/bin/plugin install contrib

RUN mkdir /var/www
ADD run /var/www/run

# Kibana
EXPOSE 9292

# Raw JSON
EXPOSE 5000

# Start logstash
CMD /var/www/run

