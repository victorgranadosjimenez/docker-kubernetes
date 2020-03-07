##Go API que proporciona la informacion del host

#creamos nuestra imagen desde nuestro dockerfile en src/
docker build -t goapi src/

#creamos el container desde esta imagen
docker run --name goaoi_container -d -p 8080:8080 goapi


#comprobar lo que tenemos en cualquier momento del proceso
kubectl get all
kubectl get nodes

##PODS
#creamos nuestro pod a traves de nuestro manifest fichero yaml
kubectl apply -f pod.yaml

##DEPLOYMENT
#crear el deploymet desde nuestor ficher yaml, levantando 10 nodos
kubectl apply -f deployment.yaml

#podemos borrar cualquier de estos nodos que kubernetes levantara otro en su lugar
kubectl delete pod nombre_completo_del_pod

##SERVICES
#crear el services, load balancer en este caso, desde nuestro fichero yaml
kubectl apply -f services.yaml
#comprobar que nuestro servicio esta corriendo y su cluster ip y puerto
kubectl get svc
