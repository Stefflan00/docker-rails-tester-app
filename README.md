**Docker Rails Simple Example**

Steps:

- clone the repo

- jump into the repo

- Select your Docker-Machine where you want to run the rails app

```
eval $(docker-machine env YOUR_MACHINE_NAME)
```

- Check if there is something running (there should nothing running on Port 80)

```
docker ps
```

- Install gems

```
bundle install
```

- build docker container

```
docker build -t data/love .
```

- run the docker container

```
docker run -d -p 80:80 -e SECRET_KEY_BASE=secretkey data/love
```

- visit the site via curl

```
curl $(docker-machine ip YOUR_MACHINE_NAME):80
```
