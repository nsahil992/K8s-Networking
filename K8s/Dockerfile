# Use an official Golang image as a builder
FROM golang:1.21 AS builder

WORKDIR /app

COPY .. .

RUN go mod tidy
RUN go build -o main .

# Use a lightweight image for production
FROM alpine:latest

WORKDIR /root/


COPY ../main .

# Ensure execution permissions
RUN chmod +x ./main

EXPOSE 8080

CMD ["./main"]
