FROM ghcr.io/labring-actions/devbox/python-3.12:6de245

RUN cd /home/sealos/project && \
rm -rf ./*
COPY /Framework/flask/3.0.3/project /home/sealos/project

RUN chown -R sealos:sealos /home/sealos/project && \
    chmod -R u+rw /home/sealos/project 

USER sealos
RUN python3 -m venv /home/sealos/project && \
    cd /home/sealos/project && \
    . bin/activate && \
    pip3 install flask && \
    deactivate 

RUN mkdir /home/sealos/.sealos
