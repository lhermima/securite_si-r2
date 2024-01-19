# Use the official Ubuntu 20.04 base image
FROM ubuntu:20.04

#Set a working directory
WORKDIR /usr/src/app

# Set non-interactive mode (important for apt to not prompt for input)
ENV DEBIAN_FRONTEND=noninteractive

#Update packages
RUN apt-get update

# Copy packages and add pwd to PATH
COPY cockroach-v23.2.0-rc.1.linux-amd64.tgz zitadel-linux-amd64.tar.gz .

# Install and run CockroachDB package
RUN tar zxvf cockroach-v23.2.0-rc.1.linux-amd64.tgz

# Install and run Zitadel package
RUN tar zxvf zitadel-linux-amd64.tar.gz

# see how to open browser to http://localhost:8080/ui/console and enter credentials (zitadel-admin@zitadel.localhost then Password1!)
# Entry point
ENTRYPOINT ./cockroach-v23.2.0-rc.1.linux-amd64/cockroach start-single-node --insecure --background --http-addr :9090 --listen-addr=localhost && ZITADEL_EXTERNALSECURE=false ./zitadel-linux-amd64/zitadel start-from-init --masterkey "MasterkeyNeedsToHave32Characters" --tlsMode disabled && /bin/bash

