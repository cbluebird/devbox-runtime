FROM ghcr.io/labring-actions/devbox/debian-ssh:d8f335

COPY /Language/go/project /home/sealos/project

RUN curl -O https://dl.google.com/go/go1.23.0.linux-amd64.tar.gz && \
    tar -xvf go1.23.0.linux-amd64.tar.gz && \
    mv go /usr/local && \
    rm go1.23.0.linux-amd64.tar.gz && \
    mkdir -p /go/bin && \
    echo 'export GOPATH=/go' >> /home/sealos/.bashrc && \
    echo 'export PATH=$PATH:/usr/local/go/bin:/go/bin' >> /home/sealos/.bashrc && \
    echo 'export GOPATH=/go' >> /root/.bashrc && \
    echo 'export PATH=$PATH:/usr/local/go/bin:/go/bin' >> /root/.bashrc && \
    chmod -R 777 /go && \
    chown -R sealos:sealos /home/sealos/project && \
    chmod -R u+rw /home/sealos/project
    
ENV GOPATH=/go
ENV PATH=$PATH:/usr/local/go/bin:/go/bin

RUN mkdir /root/.sealos