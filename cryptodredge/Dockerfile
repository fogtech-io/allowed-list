FROM nvidia/cuda:9.1-base

RUN apt-get update > /dev/null \
    && apt-get install wget -y \
    && rm -rf /var/lib/apt/lists/* \
    && mkdir /root/src \
    && wget "https://github.com/technobyl/CryptoDredge/releases/download/v0.20.1/CryptoDredge_0.20.1_cuda_9.1_linux.tar.gz" -O /root/src/miner.tar.gz \
    && tar xvf /root/src/miner.tar.gz -C /root/src/ \
    && find /root/src -name 'CryptoDredge' -exec cp {} / \; \
    && rm -rf /root/src/

COPY run.sh /

ENTRYPOINT ["/run.sh"]
