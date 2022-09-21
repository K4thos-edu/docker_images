FROM golang:1.15-alpine AS build

ADD src/*.go /go

# Download necessary Go modules
#COPY go.mod ./
#COPY go.sum ./
#RUN go mod download

# Test before compilation
#RUN go test --cover -v ./...

# Compile application
RUN CGO_ENABLED=0 go build -o app

######

FROM scratch
WORKDIR /
COPY --from=build /go/app /app
EXPOSE 80
ENTRYPOINT ["/app"]
