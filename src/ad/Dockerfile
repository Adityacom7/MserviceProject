FROM eclipse-temurin:21-jdk AS builder
WORKDIR /usr/src/app/
COPY . .
COPY ./pb ./proto
RUN chmod +x gradlew
RUN ./gradlew 
RUN ./gradlew downloadrepos 
RUN chmod +x ./gradlew
RUN ./gradlew installDist -PprotoSourceDir=./proto
FROM eclipse-temurin:21-jre AS release
WORKDIR /usr/src/app/   

COPY --from=builder /usr/src/app/ ./
ENV AD_PORT=8080
ENV FEATURE_FLAG_GRPC_SERVICE_ADDR=eatureflagservice:50053
ENTRYPOINT [ "./build/install/opentelemetry-demo-ad/bin/Ad" ]