FROM ubuntu:14.04
MAINTAINER Rocky TSANE <tzrocky@yahoo.fr>
RUN apt-get update
RUN apt-get upgrade -y
RUN mkdir -p /api-bracelet
WORKDIR /api-bracelet
ENV FLASK_APP  python _main_.py
ENV FLASK_RUN_HOST 0.0.0.0
RUN apk add --no-cache gcc musl-dev linux-headers
RUN apt-get install -y python python-setuptools python-pip
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
RUN pip install bottle
RUN pip install _version
CMD python _main_.py
COPY . .
CMD ["flask", "run"]
docker build -t api-bracelet .
docker run api-bracelet

#FROM python:3
#ADD my_script.py /
#RUN apk add --no-cache gcc musl-dev linux-headers
#RUN apt-get install -y python python-setuptools python-pip
#COPY requirements.txt requirements.txt
#RUN pip install -r requirements.txt
#RUN pip install pystrich
#CMD [ "python", "./_main_.py" ]
