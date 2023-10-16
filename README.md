# Projet1DevOps
Voici une description du fonctionnement du code du serveur et des deux clients :

**Code du Serveur (`Serveur.java`)** :
1. Le serveur crée un `ServerSocket` lié au port 2009.
2. Il accepte deux connexions clients (`clientSocket1` et `clientSocket2`) en utilisant `serverSocket.accept()`.
3. Le serveur lit une image depuis le disque et la divise en deux parties égales.
4. Il crée des flux de sortie (`out1` et `out2`) pour envoyer les deux parties d'images aux clients.
5. Les parties d'image sont converties en tableaux de bytes et envoyées aux clients.
6. Le serveur attend de recevoir les parties filtrées des clients.
7. Une fois les parties filtrées reçues, il les assemble en une seule image.
8. L'image finale est sauvegardée sous le nom "filtered_image.jpg".
9. Toutes les connexions et les flux sont fermés, et un message est affiché.

**Code du Client 1 (`Client1.java`)** :
1. Le client 1 se connecte au serveur à l'adresse IP "192.168.1.151" et au port 2009.
2. Il reçoit une partie d'image du serveur.
3. Il applique un filtre gaussien à la partie d'image reçue.
4. La partie filtrée est renvoyée au serveur.
5. Le client ferme la connexion et les flux de données.

**Code du Client 2 (`Client2.java`)** :
1. Le client 2 se connecte au serveur à l'adresse IP "192.168.1.149" et au port 2009.
2. Il reçoit une partie d'image du serveur.
3. Il applique un filtre gaussien à la partie d'image reçue.
4. La partie filtrée est renvoyée au serveur.
5. Le client ferme la connexion et les flux de données.

En résumé, le serveur divise une image en deux parties, envoie ces parties aux deux clients, reçoit les parties filtrées de chaque client, les assemble en une image finale, et sauvegarde cette image. Les clients reçoivent leur partie d'image, appliquent un filtre gaussien à celle-ci, et renvoient la partie filtrée au serveur.
