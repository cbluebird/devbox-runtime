FROM ghcr.io/labring-actions/devbox/debian-ssh:d8f335

COPY /Language/rust/project /home/sealos/project

USER sealos
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y 

USER root

RUN apt-get update && \
    apt-get install -y build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    echo 'export PATH=/home/sealos/.cargo/bin:$PATH' >> $HOME/.bashrc && \
    echo 'source /home/sealos/.cargo/env' >> $HOME/.bashrc && \
    chown -R sealos:sealos /home/sealos/project && \
    chmod -R u+rw /home/sealos/project