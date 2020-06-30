#To run the project:

Install all dependencies for udacity-c3-frontend, udacity-c3-restapi-feed, udacity-c3-restapi-user (npm install)

#Navigate to udacity-c3-deployment/docker

Set the environment variables (These variables will be used by docker-compose):

AWS_BUCKET: ___INSERT_AWS_BUCKET___
AWS_PROFILE: ___INSERT_AWS_PROFILE___
AWS_REGION: ___INSERT_AWS_REGION___
JWT_SECRET: ___INSERT_JWT_SECRET___
POSTGRESS_DB: ___INSERT_POSTGRESS_DB___
POSTGRESS_HOST: ___INSERT_POSTGRESS_HOST___

#Navigate to udacity-c3-deployment/k8s

Set the same variables on env-configmap.yaml

Run the following command:

kubectl apply -f aws-secret.yaml && kubectl apply -f env-configmap.yaml && kubectl apply -f env-secret.yaml && kubectl apply -f backend-feed-deployment.yaml && kubectl apply -f backend-feed-service.yaml && kubectl apply -f backend-user-deployment.yaml && kubectl apply -f backend-user-service.yaml && kubectl apply -f frontend-deployment.yaml && kubectl apply -f frontend-service.yaml && kubectl apply -f reverseproxy-deployment.yaml && kubectl apply -f reverseproxy-service.yaml  && kubectl apply -f pod-example/pod.yaml