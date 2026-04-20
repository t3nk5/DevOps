"# DevOps" 

Partie 1
ex1

1.3 docker ps perme tde voir les conteneur lancés

1.4 On peut voir la page de défaut nginx

1.6 docker ps -a permet de lister tout les conteneurs, cela comprend ceux arrétés.

1.8 docker run --rm -d -p 8080:80 nginx:alpine permet de supprimer le conteneur dès qu'il est down

ex2

2.5 L'image alpine fait 26,9mb et monsite-v1 fait 26mb. 

2.6 Un seul layer a été ajouté (le copy index.html)

2.7 L'image Alpine a été télécharger depuis le cache alors que l'index.html que j'ai modifié a été réexécutée


ex3

3.1 Le conteneur étant supprimé, le volume a été supprimé, donc le fichier aussi

3.2 Le fichier html que j'ai créer est directement disponible via le navigateur, pas besoin de redémarrer ou de rebuild.

3.5 Le contenu du fichier est perssistant

3.6 Le volume est sauvegardé ici Mountpoint": "/var/lib/docker/volumes/mes-donnees/_data

3.7 Le volume ne doit pas être utilisé actuellement. Il faut donc s'en assurer en regardant quel docker utilise le volume


ex4

4.1 Les 3 réseaux créés automatiquement sont bridge, host, none

4.4 Comme docker possède un DNS interne, on peut passer par les adresses DNS au lieu des IPs

4.5 Comme les réseaux docker sont isolés, la résolution DNS ne marche pas 

4.6 La commande qui permet de connecter client-externe à mon-reseau après son démarrage est: docker network connect mon-reseau client-externe


EX5

5.3 L'odre permet d'optimiser le tempsde lancement et la modification avant lancement. Quand requirements.txt ne change pas, docker réutilise le layer pip install.
Si app.py est modifié cela fait un rebuild rapide. Sinon cela réinstalle toutes les dépendances, c'est donc un peu pls lent.

5.6 Comme on n'envoie pas la variable d'environnement APP_ENV quand on lance le docker, la variable est la varaible par défaut dans le code, cela renvoie "Environnement : développement"

5.7 L'image  pèse 197MB sur le disque. Pour réduire l'image, on pourrait de baser sur une image alpine et installé les dépendances minimales ou installé les dépendances dans une étape appart pour que les dépendances soient installés séparemment et donc pas a chaque lancement.



EX6

6.5 La commande est docker compose up -d, il faut la lancer à la racine du dossier, la ou est le docker-compose

6.6 Actualiser permet d'incrémenter le compteur, alors que le /refresh refresh le compteur à 0.

6.7 Le compteur n'est pas remis à 0 car ils se sont trouve dans un volume persistant. Les données sont enregistrés dans redis-data/data .

6.8 La commande qui permet de voir les logs en temps réel est docker compose logs -f

6.9 La commande qui permet d'entrer dans le conteneur web pour y ouvrir un shell interactif via Compose est docker compose exec web sh

6.10 La commande qui supprime les conteneurs, réseaux et volumes de la stack est docker compose down -v


EX7

7.2 Le fichier .env contient des mots de passe et données snesible, il est préférable de ne pas le push sur un git pour une sécurité optimale.
