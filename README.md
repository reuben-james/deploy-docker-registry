# deploy-docker-registry

This project gives you examples for running your own local distribution image to act as a `local` registry. 

### Run the image in docker

```
docker run -d -p 5000:5000 --restart always --name registry registry:2
```

### Compose the registry

```
cd compose
docker compose up -d
```

### tag and push an image to the local registry

```
docker pull ubuntu
docker tag ubuntu localhost:5000/ubuntu
docker push localhost:5000/ubuntu
```

List all images
```
curl -X GET http://localhost:5000/v2/_catalog | jq
```