FROM python:2.7
ENV PYTHONUNBUFFERED 1
#NOTE:
#if you use company proxy please configure the ENV
#else if you use your own connection just remove the ENV
ENV http_proxy 'http://192.168.8.7:3128'
ENV HTTP_PROXY 'http://192.168.8.7:3128'
ENV https_proxy 'http://192.168.8.7:3128'
ENV HTTPS_PROXY 'http://192.168.8.7:3128'
RUN mkdir /consumer
WORKDIR /consumer
COPY requirements.txt /consumer/
COPY . /consumer
RUN pip --default-timeout=60 install -r requirements.txt
EXPOSE 5432
CMD ["python", "kafka_consumer.py", "runserver", "0.0.0.0:8000"]
