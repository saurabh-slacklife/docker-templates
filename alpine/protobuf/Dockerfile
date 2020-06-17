From ubuntu

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update -y && apt install wget unzip tar -y
WORKDIR /protoc/
RUN wget https://github.com/protocolbuffers/protobuf/releases/download/v3.12.3/protoc-3.12.3-linux-x86_64.zip && \
unzip protoc-3.12.3-linux-x86_64.zip
