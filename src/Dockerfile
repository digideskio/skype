FROM ubuntu:14.04
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    DEBIAN_FRONTEND=noninteractive \
    QT_X11_NO_MITSHM=1 \
    NO_AT_BRIDGE=1 \
    SKYPE_VERSION=4.3.0.37

RUN set -x \

    # Prepare system

    && apt-key adv --keyserver keyserver.ubuntu.com --recv 7212620B \
    && echo "deb http://archive.canonical.com/ $(lsb_release -cs) partner" >> /etc/apt/sources.list \
    && dpkg --add-architecture i386 \
    && apt-get update \

    # Install packages

    && apt-get install -y \
           pulseaudio:i386 \
           skype:i386=$SKYPE_VERSION* \

    # Clean

    && rm -rf \
           /var/lib/apt/lists/*

COPY ./rootfs /

ENTRYPOINT [ "/entrypoint.sh" ]
