FROM semaphoreui/semaphore:latest
USER root
RUN /sbin/apk add --no-cache \
    rsync \
    docker \
    py3-pip \
    py3-requests \
    py3-dockerpty
USER semaphore
RUN pip3 install requests