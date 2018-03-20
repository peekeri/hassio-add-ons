FROM homeassistant/armhf-base:latest

ENV LANG C.UTF-8

RUN apk add --no-cache python3 gcc
RUN apk add --no-cache python3-dev
RUN apk add --no-cache musl-dev
RUN apk add --no-cache linux-headers

RUN apk add --no-cache bluez bluez-deprecated

RUN pip3 install --upgrade setuptools
RUN pip3 install ruuvitag-sensor


# Copy data for add-on
COPY run.sh /
COPY collector.py /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]

