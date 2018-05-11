FROM quay.io/hephyci/base:v0.3.7

ENV CLOUD_SDK_REPO="cloud-sdk-xenial" \
	GCLOUD_CREDENTIALS_FILE="clusterator.json" \
	GCLOUD_PROJECT_ID="hephy-e2e-leasable" \
	NUMBER_OF_CLUSTERS=1 \
	NUM_NODES="3" \
	MACHINE_TYPE="n1-standard-1" \
	ZONE="us-central1-a" \
	SUBNETWORK="default"

RUN echo "deb http://packages.cloud.google.com/apt $CLOUD_SDK_REPO main" | tee /etc/apt/sources.list.d/google-cloud-sdk.list && \
	curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - && \
	apt-get update -y && apt-get install -y google-cloud-sdk

COPY . /

CMD ./create
