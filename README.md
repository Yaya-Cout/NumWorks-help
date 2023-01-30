---
title: Aide NumWorks
author: Yaya.Cout, contributeur Upsilon
date: 28 janvier 2023
---

## Disclaimer

Cette aide est non exhaustive et peut contenir des erreurs. Si vous trouvez une
erreur ou si votre problème n'est pas résolu/couvert, n'hésitez pas à rejoindre
le [serveur Discord] (ouvrez un post dans le forum `#help`).

## Introduction

Ce guide a pour but de vous aider à résoudre les problèmes que vous pouvez
rencontrer avec votre calculatrice. Si vous avez un problème qui n'est pas
résolu/couvert par ce guide, n'hésitez pas à rejoindre le
[serveur Discord] (ouvrez un post dans le forum `#help`).

## Problèmes courants

### Ma NumWorks est-elle déverrouillée ?

Pour savoir si votre NumWorks est déverrouillée, il suffit d'appuyer sur
RESET et 6 simultanément (le RESET doit être relâché avant le 6).

- Si la calculatrice affiche `numworks.com/rescue`, alors elle est verrouillée.
- Si elle affiche un écran noir et une LED rouge, alors elle est déverrouillée.

> **_NOTE :_** Si aucune des deux situations ne se produit, réessayez d'appuyer
> sur les touches RESET et 6.

### Déverrouiller ma NumWorks

> **_NOTE :_** Cette section est en cours de rédaction.

<!-- TODO -->

#### Ma calculatrice reste bloquée sur le bootloader après le downgrade

Si votre calculatrice reste bloquée sur le bootloader d'Epsilon (écran
`numworks.com/rescue`) après avoir effectué un downgrade après avoir appuyé sur
RESET, c'est que votre calculatrice est protégée contre le downgrade. Dans ce
cas, vous avez deux options :

- Vous pouvez remettre Epsilon en faisant une mise à jour depuis le
  [site officiel de NumWorks].
- Vous pouvez déverrouiller votre NumWorks avec un Raspberry Pi. Pour plus
  d'informations, consultez la section
  [Déverrouiller avec un Raspberry Pi](#déverrouiller-avec-un-raspberry-pi).

#### Déverrouiller avec un Raspberry Pi

Pour déverrouiller votre NumWorks avec un Raspberry Pi, vous devez suivre les
instructions sur le [Tutoriel de déverrouillage de Ti-Planet].

##### Error: Error connecting DP: cannot read IDR

Si vous obtenez l'erreur `Error: Error connecting DP: cannot read IDR` lorsque
vous essayez de déverrouiller votre NumWorks avec un Raspberry Pi, c'est que
vos câbles ne sont pas branchés correctement. Vérifiez que les câbles touchent
bien les pads de la calculatrice et que les câbles sont bien branchés sur le
Raspberry Pi.

### Installation d'Omega

#### Comment installer Omega ?

Pour installer Omega, votre NumWorks doit être déverrouillée. Si vous ne savez
pas si votre NumWorks est déverrouillée, consultez la section
[Ma NumWorks est-elle déverrouillée ?](#ma-numworks-est-elle-déverrouillée).

À cause d'un problème avec le site d'Omega, vous devez aller en mode de
récupération (à l'aide du site d'Omega) pour installer Omega. Pour plus
d'informations, consultez la section [Mode de récupération].

> **_NOTE :_** Cette maniplulation n'est pas nécessaire si vous avez une
> version d'Omega inferieure ) 2.0.0 ou si vous avez une version d'Epsilon
> antérieure à 16.0.0.

Une fois que vous êtes en mode de récupération, vous pouvez installer Omega
normalement :

1. Accédez au [site d'Omega] et cliquez sur `DETECT CALCULATOR` et sélectionnez
   votre NumWorks.

> **_NOTE :_** Si vous avez déjà connecté votre NumWorks au site d'Omega, ce
> bouton pourrait ne pas être visible. Dans ce cas, passez à l'étape 2.

2. Cliquez sur `INSTALL OMEGA`.
3. Attendez que l'installation soit terminée.

Une fois que l'installation est terminée, votre NumWorks devrait redémarrer
automatiquement. Si ce n'est pas le cas, redémarrez votre NumWorks en appuyant
sur RESET. Omega est maintenant installé sur votre NumWorks.

#### Ma NumWorks redémarre sans cesse quand le site d'Omega est ouvert

C'est un problème connu. Il est dû au fait que votre NumWorks tourne sous
Epsilon 19, qui n'est pas compatible avec le site d'Omega. La façon de résoudre
ce problème dépend de votre configuration :

- Si votre calculatrice est verrouillée, vous devez la Déverrouiller pour pouvoir
  installer Omega. Pour plus d'informations, consultez la section
  [Déverrouiller ma NumWorks](#Déverrouiller-ma-numworks).

- Si votre calculatrice est déverrouillée, vous pouvez installer Omega à partir
  de la section [Comment installer Omega ?](#comment-installer-omega).

Si vous ne savez pas si votre NumWorks est déverrouillée, consultez la section
[Ma NumWorks est-elle déverrouillée ?](#ma-numworks-est-elle-déverrouillée).

#### L'installation d'Omega n'avance pas

Si la barre de progression de l'installation d'Omega ne bouge pas, c'est qu'il
y a eu un problème lors de l'installation. Cela est surement dû à un problème
dans le site d'Omega. Pour résoudre ce problème, suivez les instructions
d'installation d'Omega à partir de la section
[Comment installer Omega ?](#comment-installer-omega).

### Mode de récupération

> **_NOTE :_** Cette section ne concerne que les NumWorks déverrouillées.

Pour aller en mode de récupération, vous devez accéder au bootloader interne
du STM32, pus installer le mode de récupération.

#### Accéder au bootloader interne du STM32

> **_NOTE :_** Cette section ne concerne que les NumWorks déverrouillées.

Pour accéder au bootloader interne du STM32, vous devez appuyer sur RESET et 6
en même temps (le RESET doit être relâché avant le 6).

Si vous avez réussi, votre NumWorks aura un écran noir et une LED rouge.

Si ce n'est pas le cas, réessayez d'appuyer sur les touches RESET et 6.

#### Installer le mode de récupération

> **_NOTE :_** Cette section ne concerne que les NumWorks déverrouillées.

Une fois dans le bootloader interne du STM32, vous devez installer le mode de
récupération. Pour ce faire, vous devez accéder au [site d'Omega] et cliquer sur
`RECOVERY`.

Une fois que vous avez cliqué sur `RECOVERY`, vous devriez voir un sélecteur
de périphérique. Sélectionnez `STM32 BOOTLOADER` et cliquez sur `Connexion`.

> **_NOTE : _** : Si vous ne voyez pas `STM32 BOOTLOADER` dans le sélecteur de
> périphérique, rendez-vous dans la section
> [Ma calculatrice n'est pas détectée/Acces denied](#ma-calculatrice-nest-pas-détectéeacces-denied).

Une fois que vous avez cliqué sur `Connexion`, vous devriez voir une barre de
progression. Lorsque la barre de progression sera complète, vous devriez voir
votre NumWorks s'allumer et afficher `RECOVERY MODE` et d'autres informations.

Bravo ! Vous avez réussi à installer le mode de récupération ! Si vous êtes allé
dans cette section à cause d'un autre problème, vous pouvez maintenant retourner
dans la section précédente.

### Ma calculatrice n'est pas détectée/Acces denied

Si votre NumWorks n'est pas détectée, cela peut être dû à plusieurs raisons. Il
est difficile de savoir laquelle et les causes ne sont pas totalement connues.
Malgré tout, il y a des solutions prouvées qui peuvent résoudre ce problème. Les
sections suivantes vous expliquent comment résoudre ce problème (Windows
uniquement).

##### Ma calculatrice n'est pas détectée sous Windows

###### Réinstaller/réparer le driver sur Windows

Pour réinstaller/réparer le driver, vous devez télécharger le fichier du driver.

Voici les liens pour télécharger le driver : (Windows)

- [Driver 64 bits]
- [Driver 32 bits]

> **_NOTE :_** Si vous ne savez pas si vous avez une version 32 bits ou 64 bits
> de Windows, vous avez probablement une version 64 bits car la majorité des
> ordinateurs sont équipés de processeurs 64 bits.

Une fois que vous avez téléchargé le driver, vous devez l'installer. Pour ce
faire, vous devez :

1. Ouvrir le fichier téléchargé.
2. Cliquer sur `Installer` (ou `Réparer` si vous avez déjà installé le driver).
3. Attendez que l'installation soit terminée.

Une fois que l'installation est terminée, redémarrez votre ordinateur et
réessayez de connecter votre NumWorks. Si le problème persiste, passez à la
section suivante.

###### Changer le driver via le gestionnaire de périphériques

Si vous avez déjà réinstallé le driver de NumWorks et avec Zadig et que le
problème persiste, vous pouvez essayer de changer le driver via le gestionnaire
de périphériques.

Pour changer le driver via le gestionnaire de périphériques, vous devez :

1. Ouvrir le gestionnaire de périphériques. (Clic droit sur le bouton
   démarrer -> Gestionnaire de périphériques)
2. Rechercher un nom de périphérique avec `STM` dans le nom. (ex: `Guillemot STM
   DFU Device`)
3. Clic droit sur le périphérique -> Mettre à jour le pilote -> Parcourir mon
   poste de travail pour rechercher des pilotes -> Choisir parmi ue liste de
   pilotes disponibles sur mon ordinateur -> NumWorks Graphing Calculator ->
   Suivant -> Fermer.
4. Vérifiez que le périphérique est bien `STM32 BOOTLOADER` ou `NumWorks
   Calculator` dans le gestionnaire de périphériques.

Une fois cela fait, redémarrez votre ordinateur et réessayez de connecter votre
NumWorks. Si le problème persiste, passez à la section suivante.


###### Installer le driver via Zadig

Si vous avez déjà installé le driver et que le problème persiste, vous pouvez
essayer d'installer le driver via Zadig.

Pour installer le driver via Zadig, vous devez télécharger Zadig.

Voici le lien pour télécharger Zadig : [Zadig]

Une fois que vous avez téléchargé Zadig, vous devez l'installer. Pour ce faire,
vous devez :

1. Ouvrir le fichier téléchargé.
2. Sélectionner `STM32 BOOTLOADER` dans le menu déroulant. (si vous ne le voyez
   pas, tentez d'afficher tous les périphériques en cochant la case `List all
   devices` dans le menu `Options`).
3. Installer le driver en cliquant sur `Reinstall WCID Driver`.

Une fois cela fait, redémarrez votre ordinateur et réessayez de connecter votre
NumWorks. Si le problème persiste, retournez à la section précédente. Si cela ne
fonctionne toujours pas, rejoignez le [serveur Discord] pour obtenir de l'aide.

#### Acces denied sur Linux

Si vous avez un message d'erreur `Acces denied` lorsque vous essayez de vous
connecter à votre NumWorks, c'est que vous n'avez pas le "driver" (il s'agit
plutôt de règles de permissions pour que l'utilisateur puisse accéder a la
calculatrice) installé. Pour résoudre ce problème, vous devez installer le
driver.

Pour installer le driver, vous devez :

1. Ouvrir un terminal.
2. Entrer la commande `sudo wget -O /etc/udev/rules.d/50-numworks-calculator.rules
    https://cdn.numworks.com/f2be8a48/50-numworks-calculator.rules` pour
    télécharger et installer le driver.

Une fois que le driver est installé, redémarrez votre ordinateur et réessayez de
vous connecter à votre NumWorks. Si le problème persiste, rejoignez le [serveur
Discord] pour obtenir de l'aide.

### Unable to claim interface

Si vous avez un message d'erreur `Unable to claim interface` lorsque vous
essayez de vous connecter à votre NumWorks, c'est que votre NumWorks est déjà
connectée à un autre site. Pour résoudre ce problème, vous devez fermer tous les
autres sites qui sont connectés à votre NumWorks. Si votre problème persiste,
tentez de redémarrer votre ordinateur.

### The bootloader has detected a crash lors du démarrage d'Upsilon

Lorsque vous essayez de démarrer Upsilon, vous avez un message d'erreur `The
bootloader has detected a crash`. Pour résoudre ce problème, vous devez
débrancher votre NumWorks le temps de sélectionner la langue et le pays.

### La batterie de ma calculatrice se décharge très vite avec l'horloge activée

Si vous avez l'horloge activée dans Omega ou Upsilon, votre batterie se décharge
très vite. Pour résoudre ce problème, vous avez deux solutions :

- Désactiver totalement l'horloge. Pour ce faire, rendez-vous dans les
  paramètres de l'heure et désactivez l'horloge.
- Passer en mode économie d'énergie. Votre horloge sera toujours active, mais
  ne consommera quasiment pas de batterie. Par contre, l'horloge dérivera
  beaucoup plus vite. Pour activer le mode économie d'énergie, rendez-vous dans
  l'application Python et lancez
```python
from time import *
setrtcmode(1)
```

### Bootloader Upsilon

Upsilon possède son propre bootloader, basé sur celui d'Omega. Le bootloader
d'Upsilon est amélioré par rapport à celui d'Omega. Les principales différences
sont :

- Le bootloader d'Upsilon s'affiche a chaque démarrage de la calculatrice.
- LE bootloader d'Upsilon a

#### This version can lock your calculator

Si vous avez un message d'erreur `This version can lock your calculator` lorsque
vous essayez de démarrer Epsilon depuis le bootloader d'Upsilon, ce message peut
être ignoré dans certains cas.

- La version d'Epsilon jusqu'à 20.2.0 devraient marcher sans problème : vous
  pouvez donc ignorer ce message à l'aide de la touche `EXE`
- Les versions d'Epsilon après 20.2.0 n'ont pas été testées au moment de la
  rédaction de ce guide. Si vous avez un message d'erreur `This version can lock
  your calculator` avec une version d'Epsilon après 20.2.0, vous pouvez tenter
  de démarrer Epsilon, mais vous risquez de vérouiller votre NumWorks.

#### Quelle est la version de mon bootloader ?

Pour savoir quelle version de bootloader vous utilisez, vous devez enter dans le
bootloader d'Upsilon à l'aide du bouton RESET. Une fois dans le bootloader,
appuyez sur la touche 5 (`About`) et vous verrez la version de votre bootloader
en bas de l'écran.

### L'écran de ma calculatrice grésille après avoir mis à jour Epsilon

<!-- TODO: Ne boot pas avec le bootloader Upsilon -->

Si l'écran de votre NumWorks clignote ou "grésille" après avoir mis à jour
Epsilon, c'est que vous utilisez une version d'Epsilon qui n'est pas compatible
avec votre bootloader.

- Si vous le bootloader d'Upsilon, passez en
  [Mode de récupération] et installez la dernière version
  d'Upsilon.
- Si vous utilisez le bootloader d'Omega, passez en [Mode de récupération] et installez la dernière version d'Omega.

### WebDFU

Le WebDFU est un outil qui permet de flasher des fichiers binaires sur votre
NumWorks. Il est utilisé lors du downgrade de votre NumWorks sur Epsilon 18.2.0
et lors de l'installation manuelle d'Omega. Pour y accéder, vous devez cliquer
[ici](https://ti-planet.github.io/webdfu_numworks/n0110/).

#### DFU DOWNLOAD failed state=10, status=15

<!-- Si vous avez un message d'erreur `DFU DOWNLOAD failed state=10, status=15` en
utilisant le WebDFU, vérifiez que votre NumWorks n'est pas connectée à un autre
site et que vous utilisez bien le [WebDFU pour NumWorks].
(`https://ti-planet.github.io/webdfu_numworks/n0110/`) -->

Si vous avez un message d'erreur `DFU DOWNLOAD failed state=10, status=15` en
utilisant le WebDFU, vérifiez que vous utilisez bien le [WebDFU pour NumWorks].
(`https://ti-planet.github.io/webdfu_numworks/n0110/`)

#### Adress 0x9000000 out of memory map

Cette erreur peut se produire dans plusieurs contextes :

- Vous essayez de downgrade votre NumWorks sur Epsilon 18.2.0. Pour résoudre ce
  problème, vous devez appuiyer sur RESET et 6 en même temps (le RESET doit être
  relâché avant le 6). Une fois cette manipulation effectuée, votre NumWorks
  devrait afficher `numworks.com/rescue`. Si ce n'est pas le cas, réessayez
  d'appuyer sur les touches RESET et 6.
- Vous utilisez le WebDFU pour installer un fichier binaire sur votre NumWorks
  déverrouillée depuis le bootloader interne du STM32 (RESET et 6). Pour
  résoudre ce problème, démarrez votre NumWorks normalement et réessayez. Si
  vous ne pouvez pas démarrer votre NumWorks normalement, vous devez installer
  le mode de récupération. Pour ce faire, rendez-vous dans la section
  [Installer le mode de récupération](#installer-le-mode-de-récupération).

### Applications externes (Omega/Upsilon)

> **Note :** Cette section concerne uniquement les applications externes d'Omega
> et Upsilon. Les applications externes d'Epsilon sont gérées différemment et ne
> sont pas couvertes par ce guide.

Les applications externes sont des applications supplémentaires qui sont
installables sur votre NumWorks déverrouillée.

#### Comment installer des applications externes ?

Pour installer des applications externes, vous devez vous rendre sur le site des
applications externes correspondant a votre système d'exploitation. Pour Omega,
rendez-vous sur [le site des applications externes d'Omega]. Pour Upsilon,
rendez-vous sur [le site des applications externes d'Upsilon].

Une fois sur le site, vous verrez une liste d'applications externes. Pour les
ajouter à votre liste d'applications, cliquez sur le bouton `Add` sous
l'application que vous souhaitez installer. Vous pouvez en sélectionner
plusieurs en même temps.

Si votre application nécessite des fichiers supplémentaires, vous devez les
ajouter à l'aide du bouton `Custom file` situé au dessis du bouton `Install`.

Vous pouvez également sélectionner un fond d'écran pour votre application en
utilisant le bouton `Image file` sous le texte `Wallpaper`. Une fois que vous
avez sélectionné votre image, vous pouvez la redimensionner en utilisant la
fenêtre qui va s'ouvrir.

Une fois que vous avez sélectionné toutes les applications que vous souhaitez
installer, cliquez sur le bouton `Install` situé à droit de la liste des
applications. Sélectionnez votre NumWorks dans la liste des périphériques et
cliquez sur `Connexion`.

> **Note :** À chaque fois que vous installez des applications externes, les
> applications déjà installées sont supprimées. Si vous souhaitez conserver vos
> applications, vous devez les installer en même temps que les nouvelles
> applications.

#### Comment désinstaller des applications externes ?

Pour désinstaller des applications externes, vous devez vous rendre sur le site
des applications externes correspondant a votre système d'exploitation (décris
dans la section précédente). Une fois sur le site, cliquez sur le bouton
`Install` sans sélectionner aucune application. Sélectionnez votre NumWorks dans
la liste des périphériques et cliquez sur `Connexion`.

Toutes les applications externes seront alors supprimées de votre NumWorks.

#### Grande quantité de fichiers lors de l'installation d'applications externes

> **Note :** Cette section concerne uniquement les calculatrices équipées d'un
> bootloader Upsilon.

Si vous avez un message d'erreur vous indiquant que vous avez une grande
quantité de fichiers et vous demandant de passer par le bootloader, vous devez
passer par le bootloader pour installer vos applications externes.

> **Note :** Cela supprimera votre slot B si vous avez un slot B.

Message d'erreur :

```text
You are writing a large amount of files to your calculator. If you are using a
recent version of Upsilon, you must go through the bootloader (reset button on
the back) to make sure that the files will not be written over running code
```

Pour résoudre ce problème, vous devez accéder au bootloader d'Upsilon. Pour
cela, appuyez sur le bouton reset situé à l'arrière de votre calculatrice. Une
fois que vous êtes dans le bootloader, appuyez sur 4 (`Installer Mode`) puis
sur 1 (`Flash slots`). Votre calculatrice va alors afficher `Waiting for slots…`
et vous pouvez alors installer vos applications externes.

#### ReferenceError: commandName is not defined

Cette erreur est due au fait que vous avez essayé d'installer une application
sur une calculatrice N0100, qui ne supporte pas les applications externes.

La raison pour laquelle elle ne les supporte pas est qu'il n'y a pas assez de
mémoire pour les installer. La mémore de la calculatrice N0100 est de 1 Mo, et
déjà, c'est insuffisant pour installer le système d'exploitation en entier.

#### Les applications externes n'apparaissent pas

> **Note :** Cette section concerne uniquement les calculatrices équipées d'un
> bootloader Upsilon avec Upsilon en slot B.

Si lorsque vous installez des applications externes, vous n'avez aucune erreur
visible sur l'ordinateur mais que les applications externes n'apparaissent pas
sur votre calculatrice avec Upsilon en slot B, c'est dû à un protection de
la mémoire.

Pour résoudre ce problème, la méthode est la même que pour le problème de
quantité de fichiers (section précédente). Vous devez accéder au bootloader
d'Upsilon en appuyant sur le bouton reset situé à l'arrière de votre
calculatrice, puis appuyer sur 4 (`Installer Mode`) puis sur 1 (`Flash slots`).
Votre calculatrice va alors afficher `Waiting for slots…` et vous pouvez alors
installer vos applications externes.

> **Note :** Si vous aviez l'erreur de quantité de fichiers, vous devez
> installer Upsilon en slot A, sinon Upsilon va s'écraser lui-même.

#### Liseuse (Upsilon)

Le système d'exploitation Upsilon est équipé d'une application `Liseuse` qui
permet de lire des livres au format `.txt` et `.urt` (format spécifique à
Upsilon permettant de mettre en forme le texte et d'afficher des expressions
mathématiques).

##### Comment installer des livres ?

Pour installer des livres, vous devez les ajouter comme des applications
externes, en tant que fichiers `.txt` ou `.urt`. Pour plus d'informations sur
l'installation d'applications externes, vous pouvez consulter la section
[Comment installer des applications externes ?](#comment-installer-des-applications-externes-).

##### Comment désinstaller des livres ?

Pour désinstaller des livres, vous devez les supprimer comme des applications
externes, en tant que fichiers `.txt` ou `.urt`. Pour plus d'informations sur
la désinstallation d'applications externes, vous pouvez consulter la section
[Comment désinstaller des applications externes ?](#comment-désinstaller-des-applications-externes-).

##### Ma calculatrice plante quand je rouvre un livre

Ce problème est dû à un bug dans le système de marque-pages de Upsilon. Pour
résoudre ce problème, vous mettre à jour Upsilon vers la dernière version beta.

### Le site de NumWorks ne fonctionne pas

Si vous rencontrez un problème avec le site de NumWorks en tentant de
transférer des scripts, vous pouvez essayer d'utiliser le [connecteur NumWorks],
qui est un site non officiel qui permet de transférer des scripts sur votre
calculatrice. Même si son interface n'est pas aussi agréable que celle du site
de NumWorks, il marche beaucoup mieux.

[Serveur Discord]: https://discord.gg/hnEqPzAJzn
[site d'Omega]: https://getomega.dev/install/latest
[Mode de récupération]: #mode-de-récupération
[Driver 64 bits]: https://cdn.numworks.com/81cc6426/numworks-driver-win64.msi
[Driver 32 bits]: https://cdn.numworks.com/2dc0a0b1/numworks-driver-win32.msi
[Zadig]: https://zadig.akeo.ie/
[WebDFU pour NumWorks]: https://ti-planet.github.io/webdfu_numworks/n0110/
[le site des applications externes d'Omega]: https://external.getomega.dev/
[le site des applications externes d'Upsilon]: https://upsilonnumworks.github.io/Upsilon-External/
[connecteur NumWorks]: https://yaya-cout.github.io/Numworks-connector/
[site officiel de NumWorks]: https://www.numworks.com/
[Tutoriel de déverrouillage de Ti-Planet]: https://tiplanet.org/forum/viewtopic.php?f=113&t=25191