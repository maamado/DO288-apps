# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# Add tags to the image
LABEL io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
io.k8s.displauy-name="Apache HTTP Server" \
io.openshift.expose-services="8080:tcp" \
io.openshift.tags="apache, httpd"

# Expose unprivileged port
EXPOSE 8080

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf && \
chgrp -R 0 /var/log/httpd /var/run/httpd && \
chmod -R g=u /var/log/httpd /var/run/httpd

# Run as unprivileged user
USER 1001
