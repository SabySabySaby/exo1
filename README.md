# exo1

1/ Créer le dokerfile dans VSCode : 
```bash
  FROM nginx:latest

  WORKDIR /usr/share/nginx/html

  COPY index.html /usr/share/nginx/html

  EXPOSE 80
   ``` 
Ne pas oublier d'enregistrer **Crtl+S**

2/ Lancer la création d'image dans le terminal VSCode :
```bash
docker build -t nom_utilisateur/image-nginx .
docker run -d -p 80:80 nom_utilisateur/image-nginx
```  
  Vérification google : **localhost:80**
  
3/ Créer un repository public sur GitHub pour stocker votre code source :
  
  Via le site DockerHub venir créer l'image sous *repositories*. Nom de l'image : **image-nginx**
  Lancer la création en publique.
  
  VSCode : 
```bash 
docker login
docker push nom_utilisateur/image-nginx 
```
4/Lancement de l'image sur internet via Minikube.

Powershell :
```bash
minikube start
kubectl create deployment nom_déployment --image image-nginx
kubectl get pod (vérifier la création)
minikube dashboard
               
kubectl expose deployment/nom_deployment --type LoadBalancer --port 80
kuberctl get svc (liste des services)
minikube service nom_deployment 
             
kuberctl scale deployment/nom_deployment --replicas 6
kubectl get pods (vérification)
minikube dashboard
```             
5/Push du projet Github:

Vscode :
```bash
git init
git remote add origin https:.......
git add .
git commit -m "descriptif"
git push -u origin master
 
```
 
  


