FROM gitlab/gitlab-runner:ubuntu-v13.6.0

LABEL author="shikanon<shikanon@tensorbytes.com>"

RUN apt-get update -y && apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common -y

RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
    apt-key fingerprint 0EBFCD88 && \ 
    add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

RUN apt-get install docker-ce docker-ce-cli containerd.io -y

RUN curl -L https://storage.googleapis.com/kubernetes-release/release/v1.19.0/bin/linux/amd64/kubectl -o /usr/bin/kubectl && chmod +x /usr/bin/kubectl

ENTRYPOINT ["/usr/bin/dumb-init" "/entrypoint"]
CMD ["run" "--user=gitlab-runner" "--working-directory=/home/gitlab-runner"]