# Setup stuff

## Application

Create the following environment variable to point to the flask app:

`export FLASK_APP=microblog.py`

## DB
A postgresql DB has been created for local development.  Dockerfile.postgres helps create the image.  To build it, run the command:

`docker build -t microblog-pg --file Dockerfile.postgres`

Then you can run the command to run the container:

`docker run --name microblog-pg -p5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=test1234 -d microblog-pg:latest`

Set the environment variable below to have the app access the local DB:

`export DATABASE_URL=postgresql://root:test1234@localhost:5432/microblog`