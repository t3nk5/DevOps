"# DevOps" 

Partie 1
ex1

1.3 docker ps permetde voir les conteneur up

1.4 On peut voir la page de défaut 

1.6 docker ps -a permet de lister tout les conteneurs, cela comprend ceux arrétés.

1.8 docker run --rm -d -p 8080:80 nginx:alpine permet de supprimer le conteneur dès qu'il est down

ex2

2.5 L'image alpine fait 26,9mb et monsite-v1 fait 26mb. 

2.6 Un seul layer a été ajouté (le copy index.html)

2.7 L'image Alpine a été télécharger depuis le cache alors que l'index.html que j'ai modifié a été réexécutée


ex3

3.1 Le conteneur étant supprimé, le volule a été supprimé, donc le fichier aussi

3.2 Le fichier html que j'ai créer est directement disponible via le navigateur, pas besoin de redémarrer ou de rebuild.

3.5 Le contenu du fichier est perssistant

3.6 Le volume est sauvegardé ici Mountpoint": "/var/lib/docker/volumes/mes-donnees/_data

3.7 Le volume ne doit pas être utilisé actuellement. Il faut donc s'en assurer en regardant quel docker utilise le volume


ex4

4.1 Les 3 réseaux créés automatiquement sont bridge, host, none

4.4 Comme docker possède un DNS interne, on peut passer par les adresses DNS au lieu des IPs

4.5 Comme les réseaux docker sont isolés, la résolution DNS ne marche pas 

4.6 La commande qui permet de connecter client-externe à mon-reseau après son démarrage est: docker network connect mon-reseau client-externe


