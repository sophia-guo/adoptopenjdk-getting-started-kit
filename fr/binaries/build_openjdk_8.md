# Construire OpenJDK 8

*Construire OpenJDK de zéro*

Si vous n'avez pas d'OpenJDK 8 dans votre VM (répertoire jdk8 ou jdk8_tl) i.e.:

```$ cd $HOME/sources/jdk8_tl```

ou

```$ cd $HOME/sources/jdk8```


ou 

```$ cd $HOME/dev/jdk8```

alors faite ce qui suit dans ce dossier :

```
$ cd $HOME/sources
or
$ cd $HOME/dev

$ hg clone http://hg.openjdk.java.net/jdk8/jdk8 jdk8
$ cd jdk8
$ chmod +x get_source.sh
$ ./get_source.sh
```

Vous verrez les résultats suivants :

```
# Repositories:  ./corba . ./hotspot ./jaxp ./jaxws ./jdk ./langtools ./nashorn 
              ./corba:   cd ./corba && hg pull -u
                    .:   cd . && hg pull -u
               ./jaxp:   cd ./jaxp && hg pull -u
            ./hotspot:   cd ./hotspot && hg pull -u
              ./jaxws:   cd ./jaxws && hg pull -u
                ./jdk:   cd ./jdk && hg pull -u
          ./langtools:   cd ./langtools && hg pull -u
            ./nashorn:   cd ./nashorn && hg pull -u
.
.
.
hotspot:   added 1 changesets with 3 changes to 3 files
            ./hotspot:   3 files updated, 0 files merged, 0 files removed, 0 files unresolved
Waiting for processes ( 19269 19296 19308 19321 19341 19347 19360 ) to terminate nicely!
          ./langtools:   13 files updated, 0 files merged, 0 files removed, 0 files unresolved
                ./jdk:   24 files updated, 0 files merged, 1 files removed, 0 files unresolved
.
.
.
```
Visitez la page [get_source](https://java.net/projects/adoptopenjdk/pages/GetSource) [dead-link]:

* [Linux (Ubuntu/Debian)](https://java.net/projects/adoptopenjdk/pages/GetSource#Debian/Ubuntu) [dead-link]

* [MacOS X](https://java.net/projects/adoptopenjdk/pages/GetSource#Mac_OS_X) [dead-link] <br/>
Note : si vous utilisez Mac OS X 10.8.5 avec XCode 5 vous devrez suivre les indications [suivantes](http://mail.openjdk.java.net/pipermail/build-dev/2013-September/010262.html). 

* [Windows](https://java.net/projects/adoptopenjdk/pages/GetSource#MS_Windows) [dead-link]<br/>

Au cas où les utilisateurs de Windows ou MacOS X ont des problèmes avec l'installation ou le téléchargement des sources, c'est une bonne idée que de créer une VM avec VirtualBox d'Oracle en suivant [ces instructions](https://java.net/projects/adoptopenjdk/pages/AdoptOpenJDKVM) [dead-link]. Construisez et continuez avec le reste des instructions jusqu'à la page "Get Sources" (puis suivez les étapes ci-dessus à partir de "Téléchargez les sources en lançant get_source.sh").

Configurez la constuction d'Openjdk (optionel si vous l'avez déjà fait)

```$ bash configure```

Construction à propre des images

```$ make clean images```

or

```$ make clean images LOG=debug     // pour afficher les information de niveau DEBUG ```

Construction des différents composants individuellement

```
$ make jdk
$ make hotspot
$ make test
```