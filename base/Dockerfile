FROM centos:centos7 

MAINTAINER Julien von Siebenthal <jsiebenthal@smart-tree.ch>

LABEL io.k8s.display-name="OpenShift Origin Centos Base" \
      io.k8s.description="This is the base image for Orthanc on Openshift."

USER root

RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all
RUN yum -y groupinstall "Development Tools"; yum clean all 

RUN mkdir -p /home/swuser

RUN groupadd -r swuser -g 433 && \
useradd -u 431 -r -g swuser -d /home/swuser -s /sbin/nologin -c "Docker image user" swuser && \
chown -R swuser:swuser  /home/swuser

USER 431 

CMD ["/bin/bash"]
