FROM photonlabs/jmeter3:base

MAINTAINER Prabu Kalaiselvam <prabu.kalaiselvam@photoninfotech.net>

EXPOSE 60000

ENTRYPOINT ["jmeter.sh","-n","-Jclient.rmi.localport=60000","-Jclient.tries=3","-Jclient.retries_delay=10000","-Jclient.continue_on_fail=true"]
