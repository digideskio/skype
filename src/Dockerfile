FROM ubuntu:16.04
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    GOSU_VERSION=1.7 \
    QT_X11_NO_MITSHM=1 \
    NO_AT_BRIDGE=1 \
    SKYPE_VERSION=4.3.0.37

RUN set -x \

    # Prepare system

    && export DEBIAN_FRONTEND=noninteractive \

    && apt-key adv --keyserver keyserver.ubuntu.com --recv 7212620B \
    && echo "deb http://archive.canonical.com/ xenial partner" >> /etc/apt/sources.list \
    && dpkg --add-architecture i386 \
    && apt-get update \

    # Install packages

    && BUILD_DEPS="curl git npm" \

    && apt-get install -y \
           $BUILD_DEPS \
           pulseaudio:i386 \
           skype:i386=$SKYPE_VERSION* \

    # Install gosu

    && curl -sLo /usr/sbin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-amd64"  \
    && chmod +x /usr/sbin/gosu \

    # Clean

    && apt-get remove -y --purge \
           $BUILD_DEPS \
    && apt-get autoremove -y --purge \

    && rm -rf \
           /var/lib/apt/lists/*

COPY ./rootfs /

ENTRYPOINT [ "/entrypoint.sh" ]
