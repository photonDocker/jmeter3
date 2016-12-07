FROM cirit/oracle-java:latest

MAINTAINER Prabu Kalaiselvam <prabu.kalaiselvam@photoninfotech.net>

ENV JMETER_VERSION=3.0
ENV JMETER_HOME=/usr/local/apache-jmeter-${JMETER_VERSION}
ENV PATH=${JMETER_HOME}/bin:${PATH}

RUN apt-get -y update && \
	apt-get -y install wget && \
	apt-get -y install unzip

RUN wget http://www.eu.apache.org/dist/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz && \
	tar -xzf apache-jmeter-${JMETER_VERSION}.tgz -C /usr/local/

  RUN wget https://jmeter-plugins.org/files/packages/jpgc-json-2.3.zip \
  	https://jmeter-plugins.org/files/packages/jpgc-sense-2.4.zip \
	https://jmeter-plugins.org/files/packages/jpgc-perfmon-2.1.zip && \
      unzip -o jpgc-json-2.3.zip -d /usr/local/apache-jmeter-3.0/ && \ 
    unzip -o jpgc-sense-2.4.zip -d /usr/local/apache-jmeter-3.0/ && \
    unzip -o jpgc-perfmon-2.1.zip -d /usr/local/apache-jmeter-3.0/
    

RUN rm -rf apache-jmeter-${JMETER_VERSION}.tgz \
			${JMETER_HOME}/bin/examples \
			${JMETER_HOME}/bin/templates \
			${JMETER_HOME}/bin/*.cmd \
			${JMETER_HOME}/bin/*.bat \
			${JMETER_HOME}/docs \
			${JMETER_HOME}/printable_docs && \
	apt-get -y remove wget && \
	apt-get -y --purge autoremove && \
	apt-get -y clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
