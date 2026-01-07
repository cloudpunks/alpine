FROM alpine:3.19@sha256:6baf43584bcb78f2e5847d1de515f23499913ac9f12bdf834811a3145eb11ca1

ENV TERM=xterm

ENTRYPOINT ["/sbin/tini", "--", "/usr/bin/entrypoint"]
CMD ["bash"]

COPY ./overlay /

RUN apk update && \
  apk upgrade -a || apk fix && \
  apk add ca-certificates curl bash bash-completion ncurses vim tar rsync shadow su-exec tini wait4x gomplate && \
  update-ca-certificates && \
  rm -rf /var/cache/apk/*
