# Kind

Para el curso de Kubernetes se va a utilizar kind para correr clusters de forma local, en el link se direcciona a la página ofcial para la instalación.

Despues de instalado, se creado un archivo de confiración en el cual se genera un cluster con un nodo worker en el que van a correr los pods.

Para inicializar el cluter se debe utilizar el comando:

`kind create cluster --config <archivo_config.yml>`

# Kubernetes

para poder configurar un pod tenemos dos tipos de configuración

- Declarativa
- Imperativa

**Imperativa**
se especifica los pasos exactos para alcanzar un estado. se indica a la herramienta lo que debe hacer para lograr un objetivo especifico en un momento dado. los caomados imperativos son aquellos que se utlizan por CLI, para realizar acciones directas.

- Ejemplo
  `kubectl run nginx --image=nginx`

**Declarativa**
Se describe el estado deseado de la infraestructura o recursos. Se define como quiere que se vea el sisitema y kubernetes se encarga de que el sistema este en el estado deseado.

Se utiliza archivos de configuración que generalmente son YAML.

Los archivos YAML o YML tienen 4 directivas

- apiVersion: indica la version del formato yml
- kind: espicifica el tipo de objeto que se está creando.
- metadata: especificar nombre, labels, namespaces, etc.
- spec: especificar todas las configutaciones que se van a aplicar al objeto.

- Ejemplo
  para aplicar un archivo yml, se dene utilizar los siguinte

`kubectl apply -f <nombre_del_archivo.yml>`

# Comandos para hacer troobleshuting con kubernets

- `kubectl get pods`
- `kubectl logs <nombre_objeto>`
- `kubectl describe <objeto> <nombre_objeto>`
- `kubectl exec pods/nginx -- comando`
- `kubectl exec -it <nombre_pod> -- <bash>`
- `kubectl port-forward <nombre_pod> <puertohost:puertopod>`

# Volumnes

Se conocen también como drivers y sirven para compartir informacion entre pods.
Existen varios tipos de volumenes o drivers.

emptyDir permite generar un volumen a nivel pod, pero este volumen va a ser montado dentro del nodo.

# Labels y Selectores

Son pares de key/value que puede asociar a los objetos, que puede ser pods, servicios, jobs, entre otros. El objetivo es organizar y seleccionar obejtos de manera flexible, el usso de los labels no afecta el funcionamiento del oibjeto.
Los labels se los coloca dentro de la directiva de metada.

Se puede utilizar para poder filtrar objetos con un label especifico, con el siguiente comando:

`kubectl get <objeto> -l key=value`
