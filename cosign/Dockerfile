FROM gcr.io/gke-release/debian-base:bookworm-v1.0.2-gke.2

RUN apt-get update && apt-get install -y curl

RUN curl -O -L "https://github.com/sigstore/cosign/releases/latest/download/cosign-linux-amd64"
RUN mv cosign-linux-amd64 /usr/local/bin/cosign
RUN chmod +x /usr/local/bin/cosign
