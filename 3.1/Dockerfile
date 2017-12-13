FROM bitnami/minideb-extras:jessie-r22

LABEL maintainer "Bitnami <containers@bitnami.com>"

ENV BITNAMI_APP_NAME=swift \
    BITNAMI_IMAGE_VERSION=3.1.1-r3 \
    PATH=/opt/bitnami/swift/bin:/opt/bitnami/python/bin:$PATH

# System packages required
RUN install_packages libc6 libtinfo5 zlib1g libstdc++6 libgcc1 libedit2 libncurses5 libxml2 libuuid1 libbsd0 liblzma5 libcurl3 libidn11 librtmp1 libssh2-1 libssl1.0.0 libgssapi-krb5-2 libkrb5-3 libk5crypto3 libcomerr2 libldap-2.4-2 libgnutls-deb0-28 libhogweed2 libnettle4 libgmp10 libgcrypt20 libkrb5support0 libkeyutils1 libsasl2-2 libp11-kit0 libtasn1-6 libgpg-error0 libffi6 python libpython2.7 clang libicu52 libsqlite3-dev

# Swift module
RUN bitnami-pkg install swift-3.1.1-1 --checksum ea953344503f80deb0a2da5ec48bbc4607912e6e10309af22477aaf4df35d4dd
RUN chown -R bitnami:bitnami /opt/bitnami/swift

COPY rootfs /

USER bitnami

WORKDIR /app

EXPOSE 80

ENTRYPOINT ["/app-entrypoint.sh"]

CMD ["swift", "app", "start"]
