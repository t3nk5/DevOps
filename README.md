"# DevOps" 

1.3 docker ps permetde voir les conteneur up

1.4 On peut voir la page de défaut 

1.6 docker ps -a permet de listr tout les conteneurs, cela comprend ceux arrétés.

1.8 docker run --rm -d -p 8080:80 nginx:alpine permet de supprimer le conteneur dès qu'il est down

2.5 L'image alpine fait 26mb et monsite-v1 fait 26.9mb

2.6 Un seul layer a été ajouté (le copy index.html)

2.7 L'image Alpine a été télécharger depuis le cache alors que l'index.html que j'ai modifié a été réexécutée

3.1 Le conteneur étant supprimé, le volule a été supprimé, donc le fichier aussi

3.2 
