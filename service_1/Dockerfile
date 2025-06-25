FROM golang:1.24-alpine AS builder

WORKDIR /app

COPY go.mod* ./
COPY go.sum* ./

RUN go mod download || true

COPY main.go .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o service1 main.go

FROM alpine:latest

RUN apk add --no-cache curl

WORKDIR /app

COPY --from=builder /app/service1 .

EXPOSE 8001

CMD ["./service1"]
