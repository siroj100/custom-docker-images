ARG VERSION
FROM woodpeckerci/woodpecker-cli:${VERSION} AS source

FROM gcr.io/distroless/base:debug
# these are taken from the source Dockerfile at 
# https://github.com/woodpecker-ci/woodpecker/blob/main/docker/Dockerfile.cli.multiarch
ENV GODEBUG=netdns=go
ENV WOODPECKER_DISABLE_UPDATE_CHECK=true
COPY --from=source . .

HEALTHCHECK CMD ["/bin/woodpecker-cli", "ping"]
ENTRYPOINT ["/bin/woodpecker-cli"]
