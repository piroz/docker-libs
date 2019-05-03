FROM nvidia/cuda:10.0-cudnn7-runtime

RUN sed -i.bak -e "s%http://[^ ]\+%http://ftp.jaist.ac.jp/pub/Linux/ubuntu/%g" /etc/apt/sources.list

RUN apt update 
RUN apt install -y python3-pip

RUN pip3 install tensorflow-gpu keras

RUN apt install -y wget
ADD mnist_cnn.py /


CMD ["python3", "/mnist_cnn.py"]