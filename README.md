# vue-app

## Deployments Vue.js application on Kubernetes

Create a new application or use the provided sample application which has been generated with the Vue CLI:

```sh
$ npm install --global vue-cli
$ vue init webpack vue-app
$ cd vue-app
$ npm run build
```

Run the application locally:

```sh
$ cd vue-app
$ npm run dev
```

Build the Docker image:

```sh
$ docker build -t vue-app .
```

Run Docker container locally:

```sh
$ docker run -d -p 8080:80 vue-app
```

Push it to DockerHub (replace the namespace/account):

```sh
$ docker login
$ docker tag vue-app magikcypress/vue-app
$ docker push magikcypress/vue-app
```

Deploy on Kubernetes. By default an image is used from DockerHub (change externalIPs on Service).


```sh
$ kubectl apply -f kube-vue.yaml
```
