FROM ubuntu:18.04
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y -q python-all python-pip
COPY requirements.txt /tmp/requirements.txt
RUN pip install -qr /tmp/requirements.txt
RUN mkdir -p /opt/webapp
COPY . /opt/webapp
WORKDIR /opt/webapp
EXPOSE 5000
CMD ["python", "app.py"]