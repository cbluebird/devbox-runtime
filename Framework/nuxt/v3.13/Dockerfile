FROM ghcr.io/labring-actions/devbox/node.js-20:255ae9
RUN cd /home/devbox/project && \
rm -rf ./*

COPY /Framework/nuxt/v3.13/project /home/devbox/project
RUN chown -R devbox:devbox /home/devbox/project && \
chmod -R u+rw /home/devbox/project  && \
chmod -R +x /home/devbox/project/entrypoint.sh

USER devbox
RUN cd /home/devbox/project && \
npm config seinstat fetch-retry-maxtimeout 4000000 && \
npm install && \
pnpm run build

USER root
RUN mkdir /home/devbox/.devbox