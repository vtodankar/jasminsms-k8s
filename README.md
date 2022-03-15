#  JasminSMS demo in K8S 
#  Install Redis. RabbitMQ, SMPP Simulator, JasminSMS containers

Simple SMS sender test

# Deployment in Kubernetes
## Minikube
```bash
minikube start
```

To enable docker
```bash
eval $(minikube docker-env)
```

## Usage to send SMS
Deploy the K8S yamls
```bash

kubectl apply -f k8s/

kubectl port-forward service/jasmin 8990:8990

kubectl port-forward service/jasmin 1401:1401

```

Follow configuration of the JasminSMS https://docs.jasminsms.com/en/latest/installation/index.html#docker

telnet localhost:8990
Configure the SMPP Connector, Route and API group and user (vikrant/password)

Make a GET request request to http://localhost:1401/send?username=vikrant&password=password&to=329408&content=hello 