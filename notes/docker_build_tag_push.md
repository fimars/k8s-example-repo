[docs](https://docs.docker.net.cn/get-started/docker-concepts/building-images/build-tag-and-publish-an-image/)

```bash
docker build -t my-username/my-image .
docker image tag my-username/my-image another-username/another-image:v1
docker push my-username/my-image:v1
```
