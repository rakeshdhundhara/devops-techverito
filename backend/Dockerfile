# Use Go Alpine image
FROM golang:1.19-alpine

# Install git (needed for some go modules)
RUN apk add --no-cache git

# Set working directory
WORKDIR /app

# Copy go.mod and go.sum first (for caching)
COPY go.mod go.sum ./

# Download all dependencies
RUN go mod download

# Copy the rest of the source code
COPY . .

# Expose the port your app uses
EXPOSE 8080

# Run the Go app
CMD ["go", "run", "main.go"]
