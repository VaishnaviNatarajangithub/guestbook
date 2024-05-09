# Stage 1: Build stage
FROM golang:1.15 as builder
WORKDIR /app
COPY . .
RUN go mod download
RUN go build -o /app/main .

# Stage 2: Final stage
FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/main /app
EXPOSE 8080
CMD ["./main"]

