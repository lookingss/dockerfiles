FROM jfloff/alpine-python

LABEL maintainer="lookings939@gmail.com"

ENV METHOD="aes-256-cfb"
ENV PASSWORD="ss_2018"
ENV PORT=10001

RUN pip install shadowsocks

EXPOSE $PORT

HEALTHCHECK --interval=30s --retries=3 --timeout=30s CMD nc -z 127.0.0.1 $PORT || exit 1

CMD ssserver -p $PORT -m $METHOD -k $PASSWORD --fast-open