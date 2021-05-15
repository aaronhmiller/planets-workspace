# API Spec workspace and Flask App for demoing APIOps

<img width="1800" alt="It's OK Pluto" src="https://user-images.githubusercontent.com/223486/118372778-13e60500-b568-11eb-97f7-cd6c557da3d4.png">

This application contains: one flask app in `app.py`. It serves up data about planets from [NASA data](https://solarsystem.nasa.gov/moons/in-depth/) at `/planets` and `/planets/<position>`. It's used in an end-to-end demonstration of Kong and should be imported into [Insomnia](https://insomnia.rest) for full-effect.

It's based on work by the amazing [Lorna Jane Mitchell](https://github.com/lornajane) and its beauty is in its simplicity & clarity. It's a training ground for originating API ideas as a specification before implementation. It has been augmented with Kong and Insomnia to show how APIOps can be leveraged to make the API Lifecycle more efficient, clear, and reliable.

<img width="1800" alt="API Lifecycle" src="https://user-images.githubusercontent.com/223486/116041967-bb83ad80-a622-11eb-9463-4546a79eba36.png">


## Running

```
FLASK_APP=app.py python -mflask run
```

In its more portable form, run it as a Docker Container:
```
docker run -d --name planets -p 5000:5000 kongaaron/flask-planets
```

## Building your own
To build and tag a new image (see deploy.sh), clone this repo and:
```
docker build -t <your_docker_hub_account>/flask-planets:1.0 -t <your_docker_hub_account>/flask-planets:latest .
```
Once you tag and build, upload to `hub.docker.com`:
`docker push <your_docker_hub_account>/flask-planets`
