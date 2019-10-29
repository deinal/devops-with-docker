FROM ubuntu:16.04 

ENV LC_ALL=C.UTF-8 

RUN apt-get update && apt-get install -y \ 
    python python-pip ffmpeg && \
    pip install --user --upgrade yle-dl && \
    apt-get purge -y --auto-remove python-pip && \
    apt-get install --reinstall python-pkg-resources && \
    rm -rf /var/lib/apt/lists/* 

WORKDIR /app

ENTRYPOINT ["/root/.local/bin/yle-dl"]
