FROM golang:onbuild

MAINTAINER Dmitry Ulyanov <swhile@ya.ru>

RUN mkdir -p /go/src/app
WORKDIR /go/src/app
ADD src/* .

CMD ["go-wrapper", "run"]
