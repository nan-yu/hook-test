# Build intermediate image for gcloud / kubectl
FROM gcr.io/google.com/cloudsdktool/google-cloud-cli:449.0.0-slim as gcloud-install

RUN apt-get update && apt-get install -y kubectl google-cloud-sdk-gke-gcloud-auth-plugin


FROM gcr.io/gke-release/debian-base:bookworm-v1.0.2-gke.2

RUN apt-get update && apt-get install -y curl bash

RUN curl -O -L "https://github.com/sigstore/cosign/releases/latest/download/cosign-linux-amd64"
RUN mv cosign-linux-amd64 /usr/local/bin/cosign
RUN chmod +x /usr/local/bin/cosign

COPY --from=gcloud-install /usr/lib/google-cloud-sdk /usr/lib/google-cloud-sdk
ENV PATH "$PATH:/usr/lib/google-cloud-sdk/bin"
