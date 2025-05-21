FROM golang:1.24-alpine

RUN apk update && apk upgrade && \
    apk add --no-cache bash

WORKDIR /var/www/backend

COPY backend/go.mod ./
COPY backend/go.sum ./
RUN go mod download


CMD ["go", "run", "."]
