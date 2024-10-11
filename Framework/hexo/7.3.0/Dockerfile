FROM ghcr.io/labring-actions/devbox/node.js-20:255ae9

RUN cd /home/devbox/project && \
rm -rf ./*

RUN mkdir -p /home/devbox/project && \
chown -R devbox:devbox /home/devbox/project && \
chmod -R u+rw /home/devbox/project

USER devbox
RUN sudo npm install -g hexo-cli && \
hexo init /home/devbox/project && \
cd /home/devbox/project && \
npm install
COPY /Framework/hexo/7.3.0/entrypoint.sh /home/devbox/project/entrypoint.sh

USER root
RUN mkdir /home/devbox/.devbox