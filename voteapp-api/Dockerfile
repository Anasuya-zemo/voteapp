FROM golang:alpine3.18

WORKDIR /go-app

COPY go.* .
RUN go mod download

copy *.go .
RUN go build -o api

EXPOSE 8080

CMD ["./api"]
