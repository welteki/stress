FROM ghcr.io/openfaas/classic-watchdog:0.3.1 AS watchdog

FROM nixery.dev/toybox/stress

COPY --from=watchdog /fwatchdog /usr/bin/fwatchdog

# Populate example here - i.e. "cat", "sha512sum" or "node index.js"
ENV fprocess="xargs stress"
# Set to true to see request in function logs
ENV write_debug="false"

EXPOSE 8080

HEALTHCHECK --interval=3s CMD [ -e /tmp/.lock ] || exit 1

CMD ["fwatchdog"]
