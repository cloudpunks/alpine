FROM alpine:3.23@sha256:8169a308ae899f69285e7214b3c2de1c1f0f091ab228b87a58040c49d8cc2b0d

ENV TERM=xterm

ENTRYPOINT ["/sbin/tini", "--", "/usr/bin/entrypoint"]
CMD ["bash"]

COPY ./overlay /

RUN apk update && \
  apk upgrade -a || apk fix && \
  apk add ca-certificates curl bash bash-completion ncurses vim tar rsync shadow su-exec tini wait4x gomplate && \
  update-ca-certificates && \
  rm -rf /var/cache/apk/*
