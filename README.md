# Enonce de l'exercice 

#### Ecrivez un manifest namespace.yml qui crée un namespace nommé production et lancez la création de ce namespace à partir du manifest 
#### Toutes vos prochaines ressources doivent être créées dans le namespace production 
####  Ecrivez un manifest pod-red.yml pour déployer un pod avec l'image mmumshad/simple-webapp-color en précisant que la color souhaitée est la rouge (red) , le pod doit posséder de label "app:web"
#### Lancez la création de deux pods 
#### Ecrivez un manifest service-nodeport-web.yml qui permettra d'exposer les pods via un service de type node port ,le nodeport devra être le 30008 et les target les ports 8080 de nos pods dont le label est "app:web"
#### Lancez la creation du service et vérifiez qu'il trouve les deux pods (champ endpoint en utilisant la commande kubectl describe)
#### Vérifier que l'application est bien disponible en ouvrant le port 30008 de votre noeud 





# Correction de l'exercice 

#### Ecrivez un manifest namespace.yml qui crée un namespace nommé production 
          voir le fichier namespace.yml 
#### lancez la création de ce namespace à partir du manifest 
          kubectl apply -f namespace.yml 
#### Ecrivez un manifest pod-red.yml pour déployer un pod avec l'image mmumshad/simple-webapp-color en précisant que la color souhaitée est la rouge (red) , le pod doit posséder de label "app:web"
          voir le fichier pod-red.yml
#### Ecrivez un manifest pod-blue.yml pour déployer un pod avec l'image mmumshad/simple-webapp-color en précisant que la color souhaitée est le bleu (bleue) , le pod doit posséder de label "app:web"
          voir le fichier pod-bleue.yml
#### lancez la création de deux pods 
          kubectl apply -f pod-red.yml -n production
          kubectl apply -f pod-blue.yml -n production  
#### Ecrivez un manifest service-nodeport-web.yml qui permettra d'exposer les pods via un service de type node port ,le nodeport devra être le 30008 et les target les ports 8080 de nos pods dont le label est "app:web"
          voir le fichier service-nodeport-web.yml
#### Lancez la creation du service et vérifiez qu'il trouve les deux pods (champ endpoint en utilisant la commande kubectl describe )
          kubectl apply -f service-nodeport-web.yml -n production
