#stage-1

FROM golang:alpine3.18 as builder

WORKDIR /go-app

COPY go.* .
RUN go mod download

copy *.go .
RUN go build -o api

#stage-2

FROM alpine:3.15

COPY --from=builder ./go-app/api /api

EXPOSE 8080

CMD ["./api"]
