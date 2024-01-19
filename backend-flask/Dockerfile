FROM python:3.10-slim-buster

# Inside container
WORKDIR /backend-flask
# docker run --rm -p 4567:4567 -it backend-flask

# Outside container -> Inside container
# Contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Installs the python images used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
COPY . .

ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]