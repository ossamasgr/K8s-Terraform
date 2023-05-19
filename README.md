# K8s-Terraform
## 1- Dockerizing the python app

## 2- Installing Minikube Using Terraform 

## 3- Deploying the solution on kubernetes
### 3.1 Create a namespace
create a namespace with a name of your choice 

```kubectl
kubectl create ns demo
```

### 3.2 Install Mysql
you can use bitnami packages to deploy mysql

```helm
helm install my-sql oci://registry-1.docker.io/bitnamicharts/mysql -n demo
```
the default name of the database : 

`my_database`

to get the password : 
```
MYSQL_ROOT_PASSWORD=$(kubectl get secret --namespace demo my-sql-mysql -o jsonpath="{.data.mysql-root-password}" | base64 -d)
echo $MYSQL_ROOT_PASSWORD
```
