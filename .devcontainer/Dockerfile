FROM mcr.microsoft.com/devcontainers/java:1-21-bullseye

RUN apt-get update && \
    apt-get install -y unzip curl && \
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install && \
    rm -rf awscliv2.zip aws && \
    apt-get clean && \
    aws configure set aws_access_key_id test --profile localstack && \
    aws configure set aws_secret_access_key test --profile localstack && \
    aws configure set region us-east-1 --profile localstack
#    python3 -m pip install --upgrade localstack
# RUN curl --output localstack-cli-4.10.0-linux-amd64-onefile.tar.gz \
#    --location https://github.com/localstack/localstack-cli/releases/download/v4.10.0/localstack-cli-4.10.0-linux-amd64-onefile.tar.gz
# RUN tar xvzf localstack-cli-4.10.0-linux-*-onefile.tar.gz -C /usr/local/bin