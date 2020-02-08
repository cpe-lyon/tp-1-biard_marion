# Administration système - TP 1

## Auteurs :

*BIARD Gauthier*

*MARION Audran*

# Exercice 2 : Prise en main de l’interpréteur de commandes


## Manuel

1) **A l’aide du manuel, identifiez le rôle de la commande which**

La commande `'which'`  renvoie le chemin d'où se trouve la commande demandée. Par exemple :
`'which ls'` nous renvoie `'/usr/bin/ls'`.

&nbsp;

2) **Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercher le terme option dans la page de manuel de which ?**

Pour cela nous devons faire d'abord taper : `'man which'` et ensuite taper : `'/mot_à_chercher'
`

&nbsp;

3) **Comment quitte-t-on le manuel ?**

Pour quitter le manuel il suffit de taper : `'q'`

&nbsp;

4) **Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?**

Il suffit de taper : `'man 6 intro'`. Cette section parle des jeux.

***
## Navigation dans l’arborescence des fichiers

1) **Allez dans le dossier /var/log**

Il  suffit de taper `'cd /var/log'`

&nbsp;

2) **Remontez dans le dossier parent (/var) en utilisant un chemin relatif**

Il  suffit de taper `'cd ..'`

&nbsp;

3) **Retournez dans le dossier personnel**

Il  suffit de taper `'cd ..'` ou bien `'cd'`

&nbsp;

4) **Revenez au dossier précédent (/var) sans utiliser de chemin**

Il  suffit de taper `'cd -'`

&nbsp;

5) **Essayez d’accéder au dossier /root ; que se passe-t-il ?**

Lorsque nous tapons `'cd /root'`, le bash nous répond : `'permission denied'`

&nbsp;

6) **Essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez**

Lorsque nous tapons `'sudo cd /root'`, le bash nous répond : `'sudo: cd: command not found'`

&nbsp;

7) **À partir de votre dossier personnel, créez l’arborescence suivante :**

![tree view](https://github.com/cpe-lyon/tp-1-biard_marion/blob/master/arborescence.png)

Pour créer des dossiers, il faut taper la commande `'mkdir nom_fichier'`. Pour créer un document, il nous suffit de taper la commande `'echo texte_à_écrire > nom_document'`

La suite de commande à taper est donc la suivante :
```
mkdir Dossier1
mkdir Dossier2
cd Dossier1
echo > Fichier1
cd ..
cd Dossier2
mkdir Dossier2.1
mkdir Dossier2.2
cd Dossier2.2
echo > Fichier2
echo > Fichier3
```

&nbsp;

8) **Revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis
Dossier1 ; que se passe-t-il ?**

Lorsque nous sommes de nouveau dans le dossier personnel, nous effectuons la commande `'rm Dossier1/Fichier1'` afin de pouvoir supprimer *Fichier1*.

Lorsque nous effectuons la commande `'rm Dossier1'`, le bash nous répond : `'cannot remove 'Dossier1/' : It's a directory'`.

&nbsp;

9) **Quelle commande permet de supprimer un dossier ?**

Pour supprimer un dossier, il faut utiliser la commande `'rmdir Dossier1/'`.

&nbsp;

10) **Que se passe-t-il quand on applique cette commande à Dossier2 ?**

Lorsque nous appliquons cette commande à *Dossier2*, le bash nous renvoie : `'failed to remove 'Dossier2/' : Directory not empty'`

&nbsp;

11) **Comment supprimer en une seule commande Dossier2 et son contenu ?**

Afin de supprimer en une seule commande le *Dossier2* et son contenu, il faut effectuer la commande : `'rm -fr Dossier2'`

****

## Commandes importantes

&nbsp;

1) **Quelle commande permet d’afficher l’heure ? A quoi sert la commande time ?**

La commande permettant d'afficher l'heure est la commande `'date'` qui affiche également la date et le fuseau horaire. Pour n'afficher que l'heure, il faut taper que : `'date +%R'`.

La commande `'time'` permet de mesurer le temps que met une commande à d'effectuer.

>Elle retourne le temps réel écoulé entre le début et la fin de l'exécution de la commande, le temps CPU et le temps CPU système

&nbsp;

2) **Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire
sur les fichiers commençant par un point ?**

Les fichiers commençant par un '.' sont des fichiers cachés.

&nbsp;

3) **Où se situe le programme ls ?**

Le programme `'ls'` se trouve dans `'/usr/bin/'`

&nbsp;

4) **Essayez la commande ll. Existe-t-il une entrée de manuel pour cette commande ? Utilisez les commandes alias ou alias pour en savoir plus sur la nature de cette commande.**

La commande 'll' retourne :
- La taille totale du contenu du dossier courant.
- Une ligne pour chaque dossier ou fichier avec en information :
  * le premier caractère désignant le type
  * les 9 caractères suivant montrant les permissions pour l'utilisateur, le groupe et d'autres
  * le nombre de liens physiques vers ce fichier/dossier
  * le nom du propriétaire et son groupe
  * sa taille en octets
  * la date de modification
  * le nom complet (pour les liens, montre aussi la cible du lien)

Il n'y a pas d'entrée manuel pour `'ll'` car il s'agit d'un alias de la commande `'ls -alF'` (ce qu'on apprend en tapant : `'alias ll'`).

&nbsp;

5) **Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?**

Il suffit d'éxecuter la commande `'ls /bin'`. (Nous pouvons éxecuter `'ls /bin | less'` afin d'afficher les fichiers page par page).

&nbsp;

6) **Que fait la commande ls .. ?**

La commande permet d'afficher tous les dossiers présent dans le dossier parent dans lequel nous sommes.

&nbsp;

7) **Quelle commande donne le chemin complet du dossier courant ?**

Il s'agit de la commande `'pwd'`.

&nbsp;

8) **Que fait la commande echo 'yo' > plop exécutée 2 fois ?**

Elle crée d'abord un fichier txt vide nommé "plop", puis elle y écrit 'yo' une seule fois.

&nbsp;

9) **Que fait la commande echo 'yo' >> plop exécutée 2 fois ?**

elle crée d'abord un fichier txt vide nommé "plop", puis elle y écrit 'yo', et puis écrit à nouveau 'yo'lorsque nous rééxecutons la commande.

&nbsp;

10) **A quoi sert la commande file ? Essayez la sur des fichiers de types différents.**

Elle permet de déterminer le type d'un fichier ou d'un document.

&nbsp;

11) **Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier
avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi :
qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?**

```
echo 'Hello Toto !' >> toto
ln toto titi
echo 'tout va bien' >> toto
```

Lorsque nous éxecutons `cat titi`, nous observons que le contenu de titi a aussi été mofidié.

Lorsque nous supprimons 'toto' nous remarquons que 'titi' existe encore avec le même contenu.

&nbsp;

12) **Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le
contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle
conséquence cela a-t-il sur tutu ?**

Lorsque nous modifions titi alors tutu est modifié et vice-versa.

Lorsque nous supprimons titi, tutu est également supprimé.

&nbsp;

13) **Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et
reprendre le défilement à l’écran ?**

Le raccourci clavier permettant d'interrompre le défilement est : `'ctrl + s'`.

Le raccourci clavier permettant de reprendrele défilement est : `'ctrl + q'`.

Le raccourci clavier permettant d'interrompre totalement est : `'ctrl + c'`.

&nbsp;

14) **Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les
lignes 10 à 20.**

`'head -5 /var/log/syslog'`.

`'tail -15 /var/log/syslog'`.

`'head -n 10 /var/log/syslog | tail -n 10'`.

&nbsp;

15) **Que fait la commande dmesg | less ?**

"dmesg | less" permet d'afficher "dmesg" mais tout en affichant page par page.

> 'dmesg' affiche les informations sur le kernel.

&nbsp;

16) **Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page
de manuel de ce fichier ?**

Il s'agit d'un fichier texte dont chaque enregistrement décrit un compte d'utilisateur. Chaque enregistrement se compose de sept champs séparés par un deux-points.


La page du manuel correspondante est : `'man passwd'`

&nbsp;

17) **Affichez seulement la première colonne triée par ordre alphabétique inverse**

`'cut -d: -f1 /etc/passwd | sort -dr'`

> 'sort -dr' permet de trier dans l'ordre alphabétique inversé.

&nbsp;

18) **Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ?**

Nous pouvons utiliser la commande `'getent passwd | grep -c "bin/bash"'`

&nbsp;

19) **Combien de pages de manuel comportent le mot-clé conversion dans leur description ?**

Lorsque nous éxecutons la commande `'man -k conversion'` nous avons la liste des pages de manuel comportant le mot-clé conversion dans la derscription. Il y en a donc 4.

> Si à la place nous éxecutons la commande `'man -k conversion | wwc -l'`, nous avons directement le nombre de pages.

&nbsp;

20) **A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine**

Nous éxecutons la commande `'sudo find / -name passwd'` afin d'avoir la liste de tous les fichiers dont le nom comprend *passwd*.

En ajoutant `'| wc -l'` à la fin de la commande, nous avons donc le nombre de fichiers qui est de 21.

> Nous appliquons la commande en **sudo** afin de comptabilisé les dossiers protégés.

&nbsp;

21) **Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier
~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null**

`find / -name passwd >~/list_passwd_list.txt 2>/dev/null`

> `>~/list_passwd_list.txt` permet d'enregister la liste dans le fichier **list_passwd_list.txt**. `2>/dev/null` permet d'afficher les erreurs dans le fichier spécial **/dev/null**

&nbsp;

22) **Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu
précédemment**

Soit nous éxecutons la commande `grep ll -r` qui nous renvoie un retour à chaque fois que *ll* apparait et il faut donc retrouver ce qui nous intéresse. Nous pouvons à la place utilisé la commande `grep 'ls -alF' -r` afin de trouver ou se trouve l'alias.

Nous obtenons donc comme réponse :

`.bashrc:alias ll='ls -alF'`

L'alias se trouve donc dans le fichier **.bashrc**

> Il existe une commande équivalente en recherche : `grep -e 'ls -alF' -d rescue`

&nbsp;

23) **Utilisez la commande locate pour trouver le fichier history.log.**

La commande à utiliser est : `locate history.log`. Le retour que nous obtenons est :

`/var/log/apt/history.log`

&nbsp;

24) **Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ?**

Nous ne pouvons pas trouver ce fichier car la commande `locate` ne scan pas tous les fichiers mais seulement les fichiers qui sont référencés dans une base de données.

Pour que la commande locate, il faut que la database soit mise à jour et pour cela, il faut soit attendre que cela se fasse automatiquement tout les jours (ou alors lors su démarrage de la machine) mais nous pouvons aussi utilisé la commande : `sudo updateb`.

&nbsp;

# Exercice 3 : Découverte de l’éditeur de texte nano

1) **Copiez le fichier /var/log/syslog dans votre dossier personnel sous le nom log.txt, puis ouvrez-le avec
nano**

Lorsque nous sommes dans le dossier personnel :

```
cp /var/log/syslog ./log.txt
nano log.txt
```

&nbsp;

2) **Remplacez toutes les occurrences du mot kernel par le mot noyau**

On appuie sur la commande : *ctrl + alt gr + \*.

On choisit le mot à remplacer. Ici : *kernel*.

On choisit le mot par lequel on le remplace. Ici : noyau.

On appuie sur *A* pour tout modifier.

Enfin on appuie sur : *ctrl + s* pour sauvergarder.

&nbsp;

3) **Déplacer les 10 premières lignes à la fin du fichier**

On se met au début du fichier puis on appuie sur `'Alt + A'` afin de poser la marque du début de la sélection. On fait la sélection avec les flèches du clavier. Une fois la sélection choisit, il faut appuyer sur la touche `'Ctrl + K'` pour couper la sélection.

Pour aller à la fin du fichier, il faut appuyer sur la touche `'maj + alt + :'`. On appuye ensuite sur la touche `'ctrl + U'` pour coller le texte.

&nbsp;

4) **Annulez cette action**

Afin d'annuler cette action, il suffit d'appuyer 2 fois sur `'alt + U'`.

> Une fois afin d'annuler le *coller* et la deuxième pour annuler le *couper*.

&nbsp;

5) **Enregistrez le fichier avant de quitter nano**

On appuie sur `'ctrl + s'` pour sauvegarder et `'ctrl +x'` pour quitter.

&nbsp;

# Exercice 4: Personnalisation du shell

1) **Commencez par créer une copie de ce fichier, que vous appellerez.bashrc_bak**

`'cp .bashrc .bashrc_backup'`

&nbsp;

2) **Editez le fichier .bashrc avec nano et décommentez la ligne force_color_prompt=yes pour activer
la couleur. Enregistrez le fichier et quittez nano.**

`'nano .bashrc'`

On utilise l'outil de recherche en appuyant sur `'ctrl + W'`, puis on tape le mot qu'on recherche : `'force_color_prompt'` puis on appuye sur`'Enter'`.

On supprime le ``#`` puis on sauvegarde et quitte le fichier en appuyant sur `'ctrl + X'`.

&nbsp;

3) **Le fichier .bashrc est lu au *démarrage* du shell ; pour le recharger, il faudrait donc se déconnecter
puis se reconnecter ; mais il existe un autre moyen : la commande source .bashrc. Testez-la, l’invite
de commande devrait immédiatement passer en couleurs.**

Nous avons bien le bash qui passe en couleur.

&nbsp;

4) **Les couleurs par défauts (surtout celle du dossier courant) ne sont pas très visibles. Dans .bashrc,
cherchez les lignes commençant par PS1= ; elles indiquent la mise en forme de l’invite de commande
(selon que l’on est en couleurs ou non).**

 **Modifiez l’invite de commande pour qu’elle s’affiche sous la forme suivante :**

![colored syntax](https://github.com/cpe-lyon/tp-1-biard_marion/blob/master/exemple.png)

  **où l’heure est affichée en violet et entre crochets, et le chemin du dossier courant en cyan**
  
On ouvre le fichier : `'nano .bashrc'`

On utilise l'outil de recherche en appuyant sur `'ctrl + W'`, on appuye sur `'alt + c'` afin de respecter la casse, puis on tape le mot qu'on recherche : `'PS1'` puis on appuye sur`'Enter'`.

On a donc:

```
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
```

On remplace donc par le code suivant :

```
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\e[95m[\t]\e[0m - \[\033[01;32m\]\u@\h\[\033[00m\]:\e[36m\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
```

Ce qui nous donne le résultat suivant :

![colored syntax](https://github.com/cpe-lyon/tp-1-biard_marion/blob/master/final.png)



