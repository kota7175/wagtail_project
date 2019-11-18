# Use an official Python runtime as a parent image
FROM django2.2:latest
LABEL maintainer="hello@wagtail.io"

# Set environment varibles
ENV PYTHONUNBUFFERED 1
ENV DJANGO_ENV dev
ENV APP_PATH /opt/apps

COPY . $APP_PATH/
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r $APP_PATH/requirements.txt

RUN useradd wagtail
#RUN chown -R wagtail ${APP_PATH}
#USER wagtail

WORKDIR $APP_PATH

RUN python manage.py collectstatic --noinput