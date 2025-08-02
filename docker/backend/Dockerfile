FROM golang:1.24-alpine AS builder

WORKDIR /app

# Копіюємо тільки go.mod і go.sum для кешу залежностей
COPY backend/go.mod backend/go.sum ./
RUN go mod download

# Тепер копіюємо весь код
COPY backend/ ./

# Будуємо бінарник
RUN go build -o backend-app .

# --- Stage 2 (мінімальний образ для запуску)
FROM alpine:3.19

WORKDIR /app

# Копіюємо з builder тільки готовий бінарник
COPY --from=builder /app/backend-app .

# Запускаємо
CMD ["./backend-app"]
