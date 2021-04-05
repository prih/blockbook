FROM debian:10

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y libzmq3-dev libsnappy-dev && \
    apt-get clean

RUN useradd -ms /bin/bash blockbook

RUN mkdir /data && chown -R blockbook: /data

WORKDIR /home/blockbook

COPY ./build/blockbook ./blockbook
COPY ./static ./static

USER blockbook

VOLUME /data
EXPOSE 9030 9130

ENTRYPOINT ["./blockbook"]