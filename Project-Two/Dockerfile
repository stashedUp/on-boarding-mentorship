#this is a sample dockerfile for a go project
FROM golang:alpine as builder
LABEL maintainer="CDE 1 <sre-team7@pearson.com>"

WORKDIR /app
COPY go.mod  ./

RUN go mod download 

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM gliderlabs/alpine:3.6

RUN apk update && apk add ca-certificates 
RUN apk add --no-cache bash
RUN apk-install mysql-client
COPY --from=builder /app/app .

ENTRYPOINT /app
