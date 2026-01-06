Kind

para poder crear el cluster con kind se utiliza el archivo de configuracion y se utiliza el siguinte comando

kind create cluster --config <archivo_config.yml>

Kubernetes para poder configurar un pod tenemos dos tipos de configuración

- Declarativa
- Imperativa

Imperativa
se especifica los pasos exactos para alcanzar un estado. se indica a la herramienta lo que debe hacer para lograr un objetivo especifico en un momento dado. los caomados imperativos son aquellos que se utlizan por CLI, para realizar acciones directas.

ejemplo
kubectl run nginx --image=nginx

Declarativa
Se describe el estado deseado de la infraestructura o recursos. Se define como quiere que se vea el sisitema y kubernetes se encarga de que el sistema este en el estado deseado.

se utiliza archivos de configuración que generalmente son YAML.

Los archivos YAML o YML tienen 4 directivas

apiVersion - indica la version del formato yml
kind - espicifica el tipo de objeto que se está creando.
metadata - especificar nombre, labels, namespaces, etc.
spec - especificar todas las configutaciones que se van a aplicar al objeto.

ejemplo
para aplicar un archivo yml, se dene utilizar los siguinte

kubectl apply -f <nombre_del_archivo.yml>

Comandos para hacer troobleshuting con kubernets

kubectl get pods
kubectl logs <nombre_objeto>
kubectl describe <objeto> <nombre_objeto>
kubectl exec pods/nginx -- comando
kubectl exec -it <nombre_pod> -- <bash>
kubectl port-forward <nombre_pod> <puertohost:puertopod>

Volumnes

Se conocen también como drivers y sirven para compartir informacion entre pods.
Existen varios tipos de volumenes o drivers.

emptyDir permite generar un volumen a nivel pod, pero este volumen va a ser montado dentro del nodo.
