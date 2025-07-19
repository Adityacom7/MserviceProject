FROM eclipse-temurin:21-jdk-alpine AS builder
WORKDIR usr/src/app/
COPY . .
RUN ./gradlew build
FROM alpine AS release
WORKDIR /usr/src/app/   
COPY --from=builder /usr/src/app/src/ad/build/install/oteldemo/bin/Ad .
ENV AD_PORT=8080
ENV FEATURE_FLAG_GRPC_SERVICE_ADDR=eatureflagservice:50053
ENTRYPOINT [ "./build/install/opentelemetry-demo-ad/bin/Ad" ]