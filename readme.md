# README.MD

# ¿Qué comando utilizaste en el paso 11? ¿Por qué?

$ git reset --hard HEAD~1

Utilizamos reset para indicar que queremos movernos de commit, --hard para indicar que queremos que los cambios afecten tanto 
a la staging area como a la working copy y HEAD~1 para indicar que el commit al que nos queremos mover es el primer ancestro.

# ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

$ git reflog
$ git reset --hard HEAD@{1}

Con $ git reflog observamos el historial de commits y con $git reset --hard HEAD@{1} indicamos que queremos ir al commit al que
HEAD apuntaba antes de donde apunta actualmente, es decir, a antes de deshacer el último commit.

# El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

El merge del paso 13 no causa ningún conflicto porque para que un merge tenga como resultado un conflicto deberían haberse realizado cambios en las mismas 
lineas del archivo en distintas ramas, con lo que git no podría decidir con que cambios quedarse. En este caso solo se habrían realizado cambios en styled.

# El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

El merge del paso 19 sí que causa un conflicto, puesto que en el momento de realizarse ese merge, se habían realizado cambios líneas coincidentes en distintas ramas, htmlify y styled.

# El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

El merge del paso 21 no causa ningún conflicto porque en master no se habría realizado ningún cambio.

# ¿Qué comando o comandos utilizaste en el paso 25?

$ git log --graph y $ git log --all --decorate --oneline --graph 

Además, también se puede configurar la configuración que queremos para el log --graph en un alias.

# El merge del paso 26, ¿Podría ser un fast forward? ¿Por qué?

Sí que podría serlo ya que las ramas master y styled forman una lista, es decir, podríamos poner ambas en forma de lista sin perder ningún commit. 
Con mover master a donde está title, master no pierde su trabajo y además absorbe los commits que ésta no tenía y title sí.

# ¿Qué comando o comandos utilizaste en el paso 27?
/*
$ git reset HEAD~1

El reset sin -- indica que NO que queremos perder los cambios de la working copy y con HEAD~1 indicamos que queremos volver al commit padre del commit 
actual, es decir, al commit previo al merge recien realizado. De este modo descartamos los cambios sin perder nuestra working copy.
*/
$ git reset --merge ORIG_HEAD

Git guarda el valor previo de HEAD en la variable ORIG_HEAD, con lo que con este comando recuperamos el estado anterior sin perder los cambios de nuestra working copy.

# Descartar los cambios

//$ git reset --hard HEAD
$ git reset --hard HEAD@{1}

# ¿Qué comando utilizaste en el paso 29? 

$ git branch -D title

# ¿Qué comando o comandos utilizaste en el paso 30?

$ git checkout HASH, en mi caso  $ git checkout 9308c8a

# ¿Qué comando o comandos utilizaste en el paso 32?

$ git reflog
$ git checkout hash

Con hash me refiero al identificador del commit donde creo el poema git-nuestro.md, que encuentro gracias al comando $ git reflog.

# ¿Qué comando o comandos utilizaste en el punto 33?

$ git reflog
$ git checkout hash

Con hash me refiero al identificador del commit donde pongo título al poema, que encuentro gracias al historial que muestra el comando $ git reflog.
