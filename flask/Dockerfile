FROM ubuntu:14.04

RUN sed -i s@http://archive.ubuntu.com/@http://mirrors.aliyun.com/@g /etc/apt/sources.list
# RUN apt-get clean
RUN apt-get update
RUN apt-get install -y python
RUN apt-get install -y python3-pip
RUN apt-get clean all

RUN mkdir -p  ~/.pip/
RUN echo "[global]\nindex-url = https://mirrors.aliyun.com/pypi/simple/\n\n[install]\ntrusted-host=mirrors.aliyun.com" > ~/.pip/pip.conf
RUN pip3 install flask

ADD hello.py /tmp/hello.py

EXPOSE 5000

CMD ["python3", "/tmp/hello.py"]
