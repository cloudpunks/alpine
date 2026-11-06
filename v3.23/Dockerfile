FROM alpine:3.23@sha256:f3d55900449227ae9e237ede521e7b665d53a253b42065ba90b9db9275e198ad

ENV TERM=xterm

ENTRYPOINT ["/sbin/tini", "--", "/usr/bin/entrypoint"]
CMD ["bash"]

COPY ./overlay /

RUN apk update && \
  apk upgrade -a || apk fix && \
  apk add ca-certificates curl bash bash-completion ncurses vim tar rsync shadow su-exec tini wait4x gomplate && \
  update-ca-certificates && \
  rm -rf /var/cache/apk/*
