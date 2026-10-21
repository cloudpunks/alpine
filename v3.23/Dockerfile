FROM alpine:3.23@sha256:132c5416901054a60a6c1f9f5073fd16dc91c8f3de1693f6be93b5912cf3ee71

ENV TERM=xterm

ENTRYPOINT ["/sbin/tini", "--", "/usr/bin/entrypoint"]
CMD ["bash"]

COPY ./overlay /

RUN apk update && \
  apk upgrade -a || apk fix && \
  apk add ca-certificates curl bash bash-completion ncurses vim tar rsync shadow su-exec tini wait4x gomplate && \
  update-ca-certificates && \
  rm -rf /var/cache/apk/*
