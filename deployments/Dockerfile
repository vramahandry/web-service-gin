FROM --platform=${BUILDPLATFORM:-linux/amd64} golang:1.23 AS builder

ARG TARGETOS TARGETARCH

WORKDIR /app/
ADD . .
RUN CGO_ENABLED=0 GOOS=${TARGETOS} GOARCH=${TARGETARCH} go build -ldflags="-s -w" -trimpath -o web-service-gin main.go

FROM scratch
WORKDIR /app/
COPY --from=builder /app/web-service-gin /app/web-service-gin
ENTRYPOINT ["/app/web-service-gin"]