FROM golang:latest

RUN apt-get update -qq && apt-get install -y vim

ENV APP_DIR /myapp
RUN mkdir $GOPATH/src/${APP_DIR}
WORKDIR $GOPATH/src/${APP_DIR}

COPY .${APP_DIR} .

RUN go get -d -v
RUN go install -v

