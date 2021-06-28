FROM ubuntu:focal

COPY ./requirements.txt /opt
COPY ./setup_node_14.sh /opt

RUN apt-get update && \
    bash /opt/setup_node_14.sh && \
    apt-get install -y \
      nodejs \
      python2 \
      python3 \
      python3-pip && \
    npm install --global yarn && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install --no-cache-dir -r /opt/requirements.txt

RUN addgroup --gid 1000 alice && adduser --gid 1000 --uid 1000 --disabled-password --gecos "" alice

USER alice

