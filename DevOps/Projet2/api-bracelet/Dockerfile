FROM ubuntu:14.04
MAINTAINER Rocky TSANE <tzrocky@yahoo.fr>
RUN apt-get update
RUN apt-get upgrade -y
RUN mkdir -p /api-bracelet
WORKDIR /api-bracelet
COPY . .
RUN apt-get install -y python python-setuptools python-pip
RUN pip install -r requirements.txt
CMD python _main_.py
docker build -t api-bracelet .
docker run api-bracelet
