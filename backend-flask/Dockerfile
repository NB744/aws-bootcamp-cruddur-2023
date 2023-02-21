FROM python:3.10-slim-buster

# Inside the container
# Make a new folder inside the container
WORKDIR /backend-flask

# Outside the  container -> Inside the container
# This contains the libraries that we want to install to run our application.
COPY requirements.txt requirements.txt

# Inside the container
# Install the python libraries used for the application.
RUN pip3 install -r requirements.txt

# Outside the container -> Inside the container
# . means everything in the current directory
# first period . - /backend-flask (outside the container)
# second period . - /backend-flask (inside the container)
COPY . .

# Set Environment Variables
# Inside the container and will remain set when the container is run.
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# 
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]