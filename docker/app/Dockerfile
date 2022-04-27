# syntax=docker/dockerfile:1

FROM golang:1.18-alpine

WORKDIR /app

RUN apk update && apk add --no-cache gcc git openssh bash

COPY go.mod ./
COPY go.sum ./
RUN go mod download

COPY . .

RUN go build -ldflags '-w -s' -o ./bin/app ./cmd/learning

EXPOSE 8080

CMD ["./bin/app"]
