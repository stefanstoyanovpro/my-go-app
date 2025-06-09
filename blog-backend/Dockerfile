# Use official Go image as builder
FROM golang:1.24-alpine AS builder

WORKDIR /app

# Copy all files to container
COPY . .

# Build the app
RUN go build -o blog-app main.go

# Use a minimal image to run the app
FROM alpine:latest

WORKDIR /app

# Copy binary from builder stage
COPY --from=builder /app/blog-app .

# Command to run
CMD ["./blog-app"]
