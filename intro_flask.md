A la découverte du WEB : 
Intro au framework Flask avec Installation et mise en page de la première page HTML (Découverte du web)
Déjà, qu’est ce qu’un framework ?
Un framework ,c’est  une bibliothèque ou un ensemble de bibliothèque facilitant le développement logiciel. Le développement logiciel va être la création d’un site web avec du HTML et du javascript entre autres.
Installation de Flask :
Sous windows :
Très important !!! : Si vous avez une version de Python 2.7 installée sur vos machines , DESINSTALLEZ là et REDEMARREZ votre machine.
Vous qui possédez un ordinateur sous Windows , l’installation peut se révéler ardue. C’est pour cela que je commence par vous.
Il existe plusieurs façons pour installer python mais en regardant et en cherchant beaucoup, la référence qui s’impose est cygwin.
Télécharger Cygwin  ici -- > https://cygwin.com/setup-x86.exe
Une fois téléchargé, commencez l’installation 
Choisissez le package python et le package wget , comme dans les écrans ci-dessous :

![Alt text](https://raw.githubusercontent.com/kwokandy/captures/master/python.png "Optional title")



 
Python











Continuez l’installation
 
Une fois l’installation terminée, démarrez une fenêtre cygwin. Si vous n’avez pas tout suivi jusqu’à présent, cygwin est un émulateur linux. Imparfait certes mais si vous voulez installer Python et Flask, c’est le plus facile et le moins contraignant , du moins pour moi (test fait via ma machine virtuelle et ma machine au travail tournant sur windows) .
La partie la plus dure est faite pour vous qui tournez sur Windows. Vous avez un environnement commun avec ceux qui tournent sur Mac ou Linux.
La même chose pour tout le monde 
Créer un répertoire python e https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.pyt aller dessus une fois crée
	mkdir python
	cd python
Pour l’installation de Flask 
	wget https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py
Vérifier que le fichier est bien present via un ls 
	ls –Altr
Si tout est présent, il faut exécuter le script
	python ez_setup.py

Vous y êtes Presque ! Tapez 
	Pip install flask
Si Flask s’installe correctement , vous devriez voir les librairies suivantes s’installer : Werkzeug et Jinja2
