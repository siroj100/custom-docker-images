ARG VERSION
FROM caddy:${VERSION}-builder AS builder

RUN xcaddy build \
    --with github.com/caddyserver/transform-encoder

FROM caddy:${VERSION}

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
