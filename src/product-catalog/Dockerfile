FROM golang:1.22-alpine AS builder
WORKDIR /usr/src/app/
COPY go.mod go.sum ./
RUN go mod download
RUN go build -o product-catalog .

FROM alpine AS release
WORKDIR /usr/src/app/

COPY ./products ./products
COPY --from=builder /usr/bin/product-catalog ./

ENV PRODUCT_CATALOG_PORT=8088
ENTRYPOINT [ "./product-catalog" ]