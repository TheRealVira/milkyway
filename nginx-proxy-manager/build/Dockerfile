FROM jc21/nginx-proxy-manager:latest
USER root
RUN pip install --upgrade certbot certbot-dns-godaddy
RUN /opt/certbot/bin/pip install acme==1.32.0