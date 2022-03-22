FROM python:3.8
ENV PYTHONUNBUFFERED 1
RUN mkdir /code

WORKDIR /code

RUN apt-get update
RUN apt-get install -y software-properties-common && apt-get update
RUN apt-get install -y python3.8-dev
RUN apt-get install -y gdal-bin libgdal-dev
ARG CPLUS_INCLUDE_PATH=/usr/include/gdal
ARG C_INCLUDE_PATH=/usr/include/gdal
COPY requirements.txt /code/requirements.txt
RUN pip install -r requirements.txt
#COPY ../gestorx/ /code

CMD python manage.py migrate
#CMD python manage.py runserver 0.0.0.0:8000
