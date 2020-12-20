# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL io.k8s.description="Basic Apache Http child image" \
      io.k8s.display-name="Apache Http Server" \
      io.openshift.expose-service="8080:http" \
      io.openshift.tags="apache, http"

RUN sed -i "s/listen 80/listen 8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/run/httpd /var/log/httpd && \
    chmod -R g=u /var/run/httpd /var/log/httpd

USER 1001
