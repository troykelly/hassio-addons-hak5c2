ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8

# Setup base
RUN apk add --no-cache \
    openssl \
    outils-md5 \
    net-tools

# Copy data
COPY run.sh /
RUN chmod a+x /run.sh

ARG C2_VERSION
WORKDIR /usr/src/app
RUN curl -L https://downloads.hak5.org/api/devices/cloudc2/firmwares/${C2_VERSION}-stable -o c2.zip && \
    unzip c2.zip

CMD [ "/run.sh" ]
