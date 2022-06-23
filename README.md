# Practica-GitHub-KC
Repositorio de la práctica de la clase de Git en el Bootcamp de mobile


•	¿Qué comando utilizaste en el paso 11? ¿Por qué? 
git reset --hard HEAD~1 porque es la forma en la que muevo la rama styled al commit anterior perdiendo los cambios realizados en el working copy

•	¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué? 
Primero un git reflog para identificar el último comit en donde estaba el archivo modificado y luego de identificarlo (334572c), se hace un git reset --hard 334572c y tiene que ser hard para que modifique el working copy.

•	El merge del paso 13, ¿Causó algún conflicto? ¿Por qué? 
No, porque la rama de styled tenía acceso a todos los commits de la rama main, por lo tanto se podía hacer un fast forward con git merge

•	El merge del paso 19, ¿Causó algún conflicto? ¿Por qué? 
Sí, porque la rama htmlify no tenía acceso a; último commit de styled que es en donde se hicieron los cambios de estilo, entonces tenemos dos versiones del mismo documento sobre las mismas líneas .

•	El merge del paso 21, ¿Causó algún conflicto? ¿Por qué? 
No hay conflicto porque al mover la rama main al commit donde está ubicado styled (merge), main tiene acceso a todos los commits visibles desde styled

•	¿Qué comando o comandos utilizaste en el paso 25? 
git log –graph o git log --graph --pretty=oneline

•	El merge del paso 26, ¿Podría ser fast forward? ¿Por qué? 
No puede ser ff porque main está debajo del último commit de la rama tittle. Es decir que main no tiene acceso al último commit de tittle y por lo tanto se tiene que crear un commit adicional hijo de ambos en donde ahora estará ubicado main.

•	¿Qué comando o comandos utilizaste en el paso 27? 
git reset HEAD~1

•	¿Qué comando o comandos utilizaste en el paso 28? 
git restore *

•	¿Qué comando o comandos utilizaste en el paso 29? 
Como en la pregunta anterior se deshizo el merge, entonces para borrar title hay que hacer un git branch- D title

•	¿Qué comando o comandos utilizaste en el paso 30? 
Primero necesitamos volver a crear title para tener con quien mergear main. Para eso se usa un git reflog y luego se identifica la última vez en donde estaba title y se coge el commit anterior. Luego, git checkout a ese commit y una vez ahí se vuelve a crear con git branch title.
Luego, una vez creada nuevamente la rama title, nos vamos a main con git checkout main y desde ahí volvemos a hacer el mergo sin ff con tittle con git merge --no-ff title y listo.

•	¿Qué comando o comandos usaste en el paso 32? 
-	git checkout main
-	git log
Se identifica el commit en donde se creo el poema
-	git checkout <dir_commit>

•	¿Qué comando o comandos usaste en el punto 33? 
-	git reflog
ubicamos el último commit en donde estaba el título y vamos al commit anterior
-	git checkout 9471c7f
Sale el mensaje: HEAD is now at 9471c7f Merge branch 'title'-2 que es justo donde recuperamos el merge del title en la pregunta 30
-	git checkout main
Para comprobar, dibujo con git log --graph --pretty=oneline el grafo y se obtiene:
*   9471c7f3211fe5bd792f4b33e261b514a33b9fb9 (HEAD -> main) Merge branch 'title'-2
|\
| * a15fcb825477e0d15f836a6964570faa046e70f7 Se agregó un título
|/
* 334572ca43d90bec61749354dad5d3d7e7c826e1 Modificando git nuestro en rama styled
* 909c253cb8e84208754a03d8ae053c3bc9f90f1d Creando el archivo inicial git-nuestro
* 05446d953d0bcbe128c5595070300c5b1796ec29 (origin/main, origin/HEAD) Initial commit
Que es el estado final, lo que se pide en la pregunta 33

