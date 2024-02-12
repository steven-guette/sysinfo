# <span style="color: darkorange;">sysinfo</span>

***<span style="color: #9683EC;">sysinfo permet d'avoir un visuel rapide sur différentes informations du système sur lequel il se trouve.</span>***

## <span style="color: orange;">Versions disponibles</span>
**sysinfo-with-update** dispose de l'affichage des mises à jour système disponibles, mais nécessite certains droits sudo à chaque exécution.

**sysinfo-without-update** ne dispose pas de l'affichage des mises à jour système, mais ne nécessite aucun droit sudo hormis 
pour l'installation des dépendances lors de la première utilisation.

## <span style="color: orange;">Dépendances</span>
Vous devez avoir les droits sudo afin d'installer les paquets nécessaires au fonctionnement du script.
Pour la version qui propose l'affichage des mises à jour, il vous faudra l'accès à deux commandes 
(Si possible en NOPASSWD via l'utilisation de visudo pour le confort d'utilisation) :
- /usr/bin/apt-get -y update

## <span style="color: orange;">Automatiser l'exécution lors de l'ouverture d'un terminal ou une connexion SSH</span>

Commencez par télécharger le dépôt puis déplacez-vous à l'intérieur de celui-ci.
``` Bash
git clone https://github.com/steven-guette/sysinfo.git
cd sysinfo
```


Déplacez ensuite le fichier que vous souhaitez utiliser dans le répertoire de votre choix en le renommant à votre convenance.
``` Bash
mv -v sysinfo-with-update répertoire/de/mon/choix/sysinfo
OU
mv -v sysinfo-without-update répertoire/de/mon/choix/sysinfo
```

Ouvrez ensuite votre fichier .bashrc **(** *<span style="color: #9683EC;">Ou autre selon le shell que vous utilisez</span>* **)** 
à l'aide d'un editeur de texte.
``` Bash
nano ~/.bashrc
```

Ajoutez à la fin du fichier la ligne suivante en indiquant le chemin réel vers le fichier **sysinfo**.
``` Bash
bash chemin/vers/sysinfo
```

Sauvegardez et sortez de votre éditeur de texte, puis mettez à jour votre fichier .bashrc 
**(** *<span style="color: #9683EC;">Ou autre encore une fois</span>* **)**.
``` Bash
source ~/.bashrc
```

Si vous avez respecté chaque étape de la configuration, **sysinfo** devrait s'exécuter à l'intérieur de votre terminal.
Lors de la première exécution, les potentiels paquets manquants pour le bon fonctionnement du script vous seront communiqués.

**Si des paquets sont manquants, ll vous sera proposé de les installer :**
- Si vous saisissez 'oui', vous devrez renseigner votre mot de passe puis les paquets s'installerons et le reste du script sera ensuite exécuté.
- Si vous saisissez 'non', les paquets ne seront pas installé et le script s'arrêtera à cause des dépendances manquantes.

**A savoir :** Ce projet a été réalisé pour un système Debian/Unbuntu, sur d'autres systèmes, 
vous devrez probablement effectuer une installation manuelle des paquets communiqués.

Une fois tout cela terminé, il s'exécutera désormais à chaque ouverture d'un nouveau terminal, 
ou si vous établissez une connexion entrante SSH vers le(s) poste(s) sur lequel il est configuré. 
