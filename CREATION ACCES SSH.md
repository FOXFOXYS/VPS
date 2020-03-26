CREATION ACCES SSHDans PuttyGen, sélectionnez RSA en Type of key to generate et mettre 4096 en numbers of bit in a generate key. Puis cliquez sur Generate.

## CREATION ACCES SSH
* * *
Il faut dans un premier temps télécharger et installer Putty (https://www.putty.org).

**1) Création des clefs ssh** 
lancer PuttyGen, sous windows : Démarrer, Putty (64-bit), Putty Gen

![01.png](../_resources/d9e23b1a0ad349aeb8ef9b6039736508.png)

Dans PuttyGen, sélectionnez RSA en Type of key to generate et mettre 4096 en numbers of bit in a generate key. Puis cliquez sur Generate.

![02.png](../_resources/e812f524802e465cb462c18f52338c24.png)

Une fois les clefs générées, les sauvegarder en faisant : Save public key et Save private key. 

**2) Démarrer Putty**

Dans la partie Host Name (or IP adress), insérez l'adresse IP de votre serveur VPS (fournie par le fournisseur). puis cliquez sur Open.

![03.png](../_resources/2e60020b86bc45cc946abda403e2d7f9.png)

Putty se connecte sur votre serveur VPS, vous devez renseigner votre nom d'utilisateur (login as)ainsi que votre mot de passe.

![04.png](../_resources/a33378bff8224c60a7c0798faa37490d.png)

Ca y est vous êtes connecté à votre serveur.

**3) Installation de votre clef SSH sur le serveur**

Nous allons modifier le fichier authorized_keys afin que vous puissiez vous connecter sans avoir à rentrer votre mot de passe à chaque connection.

Pour celà se rendre dans le répertoire caché SSH :
tapez **cd .ssh** suivi de la touche entrée  Puis tapez **nano authorized_keys** suivi de la touche entrée

![05.png](../_resources/10b5dc1376044002b86f62f37da7f98e.png)

Dans Puttygen, copiez dans le presse papier votre clef RSA qui doit commencer par ssh-rsa (onglet Key), puis retournez dans votre terminal et dans nano, copiez votre clef en appuyant simultanèment sur les touches **SHIFT et INSER** (ou faire un clique droit).

![06.png](../_resources/f4a827ce6e354386a85b69f307e5d4ca.png)

Une fois la clé copiée, enregistrez en faisant **CTRL +O** et quitter nano en faisant **CTRL + X**

Puis quittez le terminal en tapant : **exit**

**4) Configuration de Putty**

1 - Dans la partie SSH / Auth / Authentification parameters, cliquez sur Browse et selectionnez votre clef RSA privé (extension PPK);

2 - Dans la partie Connection / Data, tapez votre nom d'utilisateur dans la case Auto-login username ;

3 - Dans la partie Session, Tapez l'adresse IP de votre serveur, le port par défaut 22 (sauf si vous avez modifié le port), connection type (cochez SSH) puis donnez un nom à votre session et enfin cliquez sur save.

![07.png](../_resources/0e31106109e6461588db20b583195022.png)

Vous voila fin prét a accéder a votre VPS sans mot de passe =) 

















