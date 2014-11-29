# Intro au framework Flask avec Installation et mise en page de la première page HTML : A la découverte du web et de l'éditeur de texte vi 

**Qu’est ce qu’un framework ?**

Un framework, c’est  une bibliothèque ou un ensemble de bibliothèque facilitant le développement logiciel. Le développement logiciel va être la création d’un site web avec du HTML et du javascript entre autres.

##Installation de Flask :

###Sous Windows :

**Très important !!! : Si vous avez une version de Python 2.7 installée sur vos machines , DESINSTALLEZ là et REDEMARREZ votre machine.**

Vous qui possédez un ordinateur sous Windows , l’installation peut se révéler ardue. C’est pour cela que je commence par vous.
Il existe plusieurs façons pour installer python mais en regardant et en cherchant beaucoup, la référence qui s’impose est cygwin.

Télécharger Cygwin  ici -- > https://cygwin.com/setup-x86.exe

Une fois téléchargé, commencez l’installation et choisissez le package python comme dans l'écran ci-dessous

![Alt text](https://raw.githubusercontent.com/kwokandy/captures/master/python.png "Python")

 Choisissez ensuite le package wget

![Alt text](https://raw.githubusercontent.com/kwokandy/captures/master/wget.png "wget")

Et enfin,  , finissez l’installation

![Alt text](https://raw.githubusercontent.com/kwokandy/captures/master/install.png "install")

 
Une fois l’installation terminée, démarrez une fenêtre cygwin. 

Cygwin comme vous avez pu le comprendre , est un émulateur linux. Imparfait certes mais pour installer Python et Flask sur Windows, c’est le plus facile et le moins contraignant , du moins pour moi (test fait via ma machine virtuelle et ma machine au travail tournant sur windows) .

La partie la plus dure est faite pour vous qui tournez sur Windows. Vous avez un environnement commun avec ceux qui tournent sur Mac ou Linux. Lancer une fenêtre Cygwin.

###Sous Windows, MacOs et Linux

Pour ceux qui sont sous Mac et Linux, ouvrez un terminal, et pour ceux qui sont sur Windows, Cygwin est déjà ouvert.

Créer un répertoire python et aller dessus , une fois crée

    mkdir python
    cd python
    
Pour l’installation de Flask , il nous faut cet outil magique qui se nomme `pip`

    wget https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py
	
Vérifier que le fichier `ez_setup.py` est bien present via un ls 

    ls –Altr
    
Si tout est présent, on peut exécuter le script que vous avez téléchargé

    python ez_setup.py

Vous y êtes Presque ! Tapez 

    pip install flask
   
Si Flask s’installe correctement , vous devriez voir les librairies suivantes s’installer : **Werkzeug** et **Jinja2**

##Votre premier script sous Flask

Vous y êtes, l'écriture de votre premier script sous `flask`. Dans le répertoire `python` crée précédemment, tapez les commandes suivantes 

    vi flasktest.py
    
Taper les lignes ci-dessous 
    ```python
    
    from flask import Flask
    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'hello world!'
    ```

Sauvegarder le fichier en pressant la touche `esc` suivi des touches `:wq`

Pour plus d'infos sur `vi` --> http://wiki.linux-france.org/wiki/Utilisation_de_vi

Voilà, ouf ! Il est temps d'éxécuter votre fichier en tapant 

    python flasktest.py
    
Vous devriez obtenir cela 

    * Running on http://127.0.0.1:5000/
    * Restarting with reloader

Faites un copié-collé de `http://127.0.0.1:5000/`dans votre browser web et vous devriez obtenir ça (voir en bas)

![Alt text](https://raw.githubusercontent.com/kwokandy/captures/master/helloworld.png "hello")

##Ta première page HTML

Pour créer votre première page 

Il te faut créer un répertoire template 
    
    mkdir templates

Une fois , fait, créer une page html

    vi first.html
    
Et mettez le code que vous souhaitez, moi j'ai mis ça 
    ```html
    <!DOCTYPE html>
    <html>
    
    <body>
    
    <h1>Ma 1ere page</h1>
    
    <p>Mon 1er paragraphe</p>
    
    <ol>
    <li>text</li>
    <li>text</li>
    <li>text</li>
    </ol>
    
    </body>
    </html>
    ```
    
Sauvegardez le fichier et donnez lui le nom que vous souhaitez, je l'ai appelé `first.html`. Pour le besoin du test, créez un nouveau fichier python et appelez comme vous le souhaitez, dans mon cas `1erpage.py`.
    ```python
    from flask import Flask,render_template
    app = Flask(__name__)
    
    @app.route('/')
    def hello_world():
      return 'hello world!'
    
    @app.route('/hello/<name>')
    def hello_paris(name):
      return render_template('first.html',name=name)
    
    if __name__ == '__main__':
      app.debug=True
      app.run()
    ```
L'option `render_template` permet d'afficher les pages web.

Pour avoir la page web

    python 1erpage.py
    
Puis `http://127.0.0.1:5000/hello/toto`dans votre browser web

![Alt text](https://raw.githubusercontent.com/kwokandy/captures/master/Capture%20d%E2%80%99%C3%A9cran%202014-11-27%20%C3%A0%2007.25.31.png)



