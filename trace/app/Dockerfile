FROM python:3.11-slim

RUN pip3 install --upgrade pip

ENV APP_HOME /app
WORKDIR $APP_HOME

# Copy local code to the container image.
COPY *.py *.txt ./

RUN pip install -r requirements.txt

CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 app:app
