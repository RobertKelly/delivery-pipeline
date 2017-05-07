# This image is based off the latest Jenkins LTS
FROM jenkinsci/jenkins:lts-alpine

USER root

# Add the docker binary so running Docker commands from the master works nicely
RUN apk -U add docker

RUN apk add --update shadow \
    && groupadd -g 50 staff \
    && usermod -a -G staff jenkins

COPY config/settings.xml /root/.m2/settings.xml

RUN install-plugins.sh antisamy-markup-formatter matrix-auth pipeline-model-definition blueocean
USER jenkins
