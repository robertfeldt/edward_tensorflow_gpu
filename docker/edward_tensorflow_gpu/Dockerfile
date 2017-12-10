FROM tensorflow/tensorflow:latest-gpu

RUN apt-get update

RUN pip2 --no-cache-dir install edward requests observations

WORKDIR "/data"

CMD "bash"
