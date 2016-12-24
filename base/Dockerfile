FROM ubuntu:14.04

MAINTAINER Julien von Siebenthal <jsiebenthal@smart-tree.ch>

LABEL io.k8s.display-name="OpenShift Origin Ubuntu Base" \
      io.k8s.description="This is the base image for Orthanc on Openshift."

USER root

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get -y install wget nano build-essential unzip cmake mercurial uuid-dev libcurl4-openssl-dev liblua5.1-0-dev libgtest-dev libpng-dev libsqlite3-dev libssl-dev libjpeg-dev zlib1g-dev libdcmtk2-dev libboost-all-dev libwrap0-dev libcharls-dev libjsoncpp-dev libpugixml-dev && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /home/swuser

RUN groupadd -r swuser -g 433 && \
useradd -u 431 -r -g swuser -d /home/swuser -s /sbin/nologin -c "Docker image user" swuser && \
chown -R swuser:swuser  /home/swuser

USER swuser 
