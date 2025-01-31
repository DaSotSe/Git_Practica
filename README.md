# Practica_GIT DSS
- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

Empleo git reset dobleguión  hard HEAD~1 para eliminar el último commit. Este comando, además, elimina los cambios en Working Copy (WC) y Staging Area (SA). Con git reset dobleguión soft HEAD~1 eliminaríamos el commit, pero mantendríamos los cambios.
Podriamos tambien optar por realizar un git reset Head-1 y posteriormente hacer un git restore en segundo lugar.

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Compruebo la eliminación del commit con git log, verifico en qué rama estoy con git branch, busco con git reflog el identificador del commit, muevo el HEAD a la posición del commit borrado con git reset --soft a91ab72 y realizo un git commit -m.

- El merge del paso 13, ¿causó algún conflicto? ¿Por qué?

No me generó conflicto porque, a pesar de que se modificaron las mismas líneas en ambos commits, el primer archivo en main permaneció sin cambios tras realizar el commit en styled. La rama styled ya contiene la versión que no se modificó en main.

- El merge del paso 19, ¿causó algún conflicto? ¿Por qué?

Sí, se generó un conflicto. El commit en HTMLIFY modifica las mismas líneas del archivo de la rama main y, por otro lado, el commit en styled también realizó una modificación sobre el archivo en main. Al fusionar, tenemos dos modificaciones sobre un mismo archivo, lo que provoca un conflicto sobre cuál debe prevalecer.

- El merge del paso 21, ¿causó algún conflicto? ¿Por qué?

No se generó conflicto. La rama main contiene el archivo original en su estado inicial y, al hacer un merge para absorber styled, no entra en conflicto, ya que no ha sufrido cambios.

- ¿Qué comando o comandos utilizaste en el paso 25?

git log --oneline --graph --all --decorate
Empleo un solo comando en el que indico:
	•	Que la visualización sea en una misma línea para interpretar mejor la gráfica.
	•	Que se muestren todos los commits de las ramas creadas.
	•	Que se muestre la información de las ramas.

- El merge del paso 26, ¿podría ser fast forward? ¿Por qué?

Sí, realizo un merge de tipo Fast Forward porque no hubo nuevos commits en main antes de la creación del merge en title. De esta manera, por defecto, ante la orden de un merge, se realiza un merge fast forward.
Se podría evitar el fast forward en caso de querer generar un nuevo commit. Como inicialmente hice un merge fast forward por equivocación, lo deshago y realizo un merge no fast forward, indicando explícitamente la fusión de main con title.

- ¿Qué comando o comandos utilizaste en el paso 27?

Realizo un git reflog para localizar el commit inmediatamente anterior y, con el hash, hago un git reset --soft <hash_commit_anterior>.

- ¿Qué comando o comandos utilizaste en el paso 28?

Para descartar los cambios en Staging Area (SA), empleo git restore --staged, pasando los cambios que estaban en SA a Working Copy.

- ¿Qué comando o comandos utilizaste en el paso 29?

Utilizo el comando git branch -D.

- ¿Qué comando o comandos utilizaste en el paso 30?

Localizo con git reflog el hash tras eliminar title, y luego ejecuto git merge --no-ff 8ae3fc1 -m.

- ¿Qué comando o comandos usaste en el paso 32?

Empleo git checkout, pero utilizando el hash de la creación del archivo en main. Primero uso git reflog y luego git checkout.

- ¿Qué comando o comandos usaste en el paso 33?

Primero utilizo git reflog y luego git checkout con el hash localizado.
