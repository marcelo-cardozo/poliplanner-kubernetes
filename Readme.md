<p align="center">
    <img src="https://user-images.githubusercontent.com/62389211/82087718-a7b79380-96be-11ea-9471-fc06cc55c845.png" alt="Poliplanner logo" width="72" height="72">
</p>

<h3 align="center">Poliplanner Kubernetes</h3>
<p align="center">
Archivos para deployar poliplanner utilizando kubernetes
</p>

### Servicios utilizados
- [Backend](https://github.com/poliplanner/poliplanner-backend)

- [Horario Service](https://github.com/poliplanner/poliplanner-horario)

## Deployar Localmente
Para instalar localmente es necesario instalar lo siguiente:
- kubectl
- minikube
Para más información dirigirse a este [link](https://matthewpalmer.net/kubernetes-app-developer/articles/install-kubernetes-ubuntu-tutorial.html)

```  
ls -d */local/ | xargs -n1 kubectl apply -f
```
### Build propios
Esta versión descarga imágenes propias de Docker Hub, en caso de que quiera crear sus propias imágenes hacer lo siguiente:
```
mkdir poliplanner
cd poliplanner
git clone git@github.com:poliplanner/poliplanner-backend.git
git clone git@github.com:poliplanner/poliplanner-horario.git

cd poliplanner-backend

# editar el nombre de las imágenes en docker-compose.build.yml

docker-compose -f docker-compose.build.yml build
docker-compose -f docker-compose.build.yml push

```

Luego es necesario modificar los deployments de tal modo a que coincidan con imágenes propias.