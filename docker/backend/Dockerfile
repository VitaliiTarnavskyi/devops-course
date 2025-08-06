FROM golang:1.24-alpine AS builder

WORKDIR /app

COPY backend/go.mod backend/go.sum ./
RUN go mod download

COPY backend/ ./

RUN go build -o backend-app .

FROM alpine:3.19

WORKDIR /app

COPY --from=builder /app/backend-app .

CMD ["./backend-app"]
