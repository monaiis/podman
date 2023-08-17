FROM golang:alpine AS builder
WORKDIR /go/src
COPY . .
RUN go get
RUN go build -o /go/bin/app 

FROM alpine
COPY --from=builder /go/bin/app /goapp/app
ENTRYPOINT [ "/goapp/app" ]
