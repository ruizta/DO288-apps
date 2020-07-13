# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

#Change port to 8080
EXPOSE 8080

#Update port label for changed port
LABEL io.openshift.expose-services="8080:http"

#Update label list for container image
LABEL io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
io.k8s.display-name="Apahe HTTP Server" \
io.openshift.expose-services="8080:http" \
io.openshift.tags="apache, httpd"

#Insert RUN instruction
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

#Change group permissions
RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
chmod -R g=u /var/log/httpd /var/run/httpd

#Add user instruction
USER 1001
