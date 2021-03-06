ARG BUILD_FROM=hassioaddons/base:7.1.0
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Copy root filesystem
COPY rootfs /

# Setup base
RUN \
    apk add --no-cache \
        hwids@edge=20191025-r0 \
        usbutils@edge=012-r1 \
        nut@edge=2.7.4-r6 \
    \
    && rm -f -r \
        /etc/nut/*.apk-new

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="Network UPS Tools" \
    io.hass.description="Manage battery backup (UPS) devices" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Dale Higgs <dale3h@addons.community>" \
    org.label-schema.description="Manage battery backup (UPS) devices" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="Network UPS Tools" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.url="https://community.home-assistant.io/" \
    org.label-schema.usage="https://github.com/hassio-addons/addon-nut/tree/master/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/hassio-addons/addon-nut" \
    org.label-schema.vendor="Home Assistant Community Addons"
