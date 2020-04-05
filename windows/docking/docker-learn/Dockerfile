############################
#    Running docker file   #
############################

## 1:
#FROM busybox
#RUN echo "building simple image"
#CMD echo "Hello container"
## busybox is a light shell
##command: docker build -t busyboxcopy .
##command: docker run --rm -ti busyboxcopy

## 2:
#FROM debian:sid
#RUN apt-get -y update
#RUN apt-get install apt-utils
#CMD ["/bin/nano", "/tmp/notes"]
##command: docker build -t takenotes .
##command: docker run --rm -ti takenotes


## 3: training example
#FROM debian:sid
#RUN apt-get -y update
#RUN apt-get install nano
#CMD ["/bin/nano", "/tmp/notes"]
# command: docker build -t nanoer .
##command: docker run --rm -ti nanoer

## 4: continuing the edit options
#FROM nanoer
#ADD notes.txt /notes.txt
#CMD ["nano", "/notes.txt"]
# command: docker build -t nanoer .
##command: docker run --rm -ti nanoer


### 5. multi staged docker
# command: docker build -t googlecounter .
##command: docker run googlecounter

FROM ubuntu:16:04 as builder
RUN apt-get update
RUN apt-get -y install curl
RUN curl https://google.com | wc -c > google_size

FROM alpine
COPY --from=builder /google_size /google_size
ENTRYPOINT echo google is this big; cat google_size
