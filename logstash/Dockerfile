FROM java:7-jre
MAINTAINER Peter Klipfel <peter@archethought.com>

echo 'deb http://packages.elasticsearch.org/logstash/1.4/debian stable main' | sudo tee /etc/apt/sources.list.d/logstash.list

RUN cd /tmp && \
    wget https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.tar.gz && \
    tar -xzvf ./logstash-1.4.2.tar.gz && \
    mv ./logstash-1.4.2 /opt/logstash && \
    rm ./logstash-1.4.2.tar.gz

RUN /opt/logstash/bin/plugin install contrib

RUN mkdir /var/www
ADD . /var/www

# Kibana
EXPOSE 9292

# Start logstash
ENTRYPOINT ["/var/www/run"]


