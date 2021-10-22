# practica-final

> Práctica final evaluable en cuestionario

## Instrucciones para la práctica final

Aunque no es obligatorio, se aconseja realizar esta práctica utilizando la consola. Si utilizas interfaces gráficas es recomendable que tengas siempre una consola abierta para algunos comandos (por ejemplo, `git status`). Ten en cuenta que en el ejercicio se te preguntará qué comandos has usado, por lo que necesitas saber el comando asociado a cada acción que
realices con la interfaz gráfica.

Puedes utilizar _git flow_ o manejar las ramas a mano, pero el modelo se tiene que basar en crear una rama para cada _feature/bug_, volcarla en _develop_ y borrarla. Éste es un proceso indirecto, puesto que en este ejercicio los volcados en develop se realizarán mediante _Pull Requests_, por tanto no los harás en tu máquina. Pero sí tendrás que bajarte _develop_ una vez mergeada y borrar la correspondiente rama local. Esto quiere decir que si usas _git flow_, lo podrás utilizar para abrir las ramas pero no para cerrarlas.

## Generalidades del ejercicio:

- Clónate en tu máquina el repositorio proporcionado por el tutor. Asegúrate de acabar teniendo _main_ y _develop_ en tu repositorio local.

- A excepción de las tareas 1, 2 y 17, recuerda crear una rama temporal para empezar cada tarea nueva que hagas. En el nombre de la rama debe aparecer el número de tarea.

- Antes de crear cada rama temporal, bájate la última versión de _develop_.

- Cuando hayas terminado cada tarea, sube la rama al servidor y crea una _Pull Request_.
Ten en cuenta lo siguiente:

    - Es importante que al crear la _PR_ marques la rama origen y la rama destino, en la parte superior. Recuerda que lo que estás solicitando es que vuelquen tu rama temporal en la rama _develop_.
    - En el título de la _Pull Request_ incluye el número de tarea, por ejemplo: #3 Texto botones login
    - Marca el check “Close branch” para solicitar que tu rama se borre del remoto después de hacer el merge.
    - No hay revisor, tú mismo debes mergear tus _Pull Request_s. Esta metodología se emplea en muchos equipos: no hay una revisión del código, pero cada integración a la rama _develop_ se hace mediante PR, a efectos de que quede un log de todas las integraciones que ha hecho cada miembro del equipo.

- Después de crear la _Pull Request_, revísala para comprobar que no hay conflictos (aparecen en la parte inferior). Si hubiera conflictos, realiza los siguientes pasos:
    - Bájate la última versión de _develop_ a tu máquina.
    - Haz que tu rama temporal _rebase_ a la rama _develop_. Esto es para fusionar el código de _develop_ y el de tu rama y provocar el conflicto (hacemos _rebase_ porque no queremos generar una ramificación sólo para resolver un conflicto).
    - Git te avisará de que hay conflictos. Resuélvelos y termina el _rebase_.
    - Cuando ya esté terminado el _rebase_ (en el prompt no ves la palabra _REBASE_), vuelve a subir tu rama temporal al remoto. Como la rama ha cambiado de forma (recuerda que el comando _rebase_ reescribe el histórico), tendrás que subirla forzando la reescritura: git push -f origin nombre_rama
    - Ve a la web del repo remoto y mira de nuevo tu _Pull Request_. Debería haber desaparecido el conflicto.

- Cuando tu rama sea mergeada a _develop_ y la _Pull Request_ marcada como “closed”, te llegará un correo electrónico. Entonces ya puedes bajarte _develop_ a tu máquina y borrar tu rama temporal.

- En algunas tareas también se te hará alguna pregunta.

- Al final de la práctica sólo pueden quedar _main_ y _develop_, tanto en remoto como en local.

## Listado de tareas y preguntas del ejercico
1. - Créate un alias, que funcione sólo en este repositorio, y que equivalga al siguiente comando:

`git log --oneline --branches --graph --remotes`
- **¿Qué comando has lanzado para crear el alias?**

2. - **¿Están las dos ramas del repositorio trackeando las correspondientes ramas remotas? ¿Qué comando has usado para averiguarlo?**

3. - Modifica el texto de los botones iniciales de login en `src/Library.java`:
· Sustituye "Librarian Login" por "Log in as librarian".
· Sustituye "Admin Login" por "Log in as administrator".
- Crea dos _commits_, uno para cada modificación.

4. - Modifica en `src/AdminLogin.java` las siguientes etiquetas del formulario:
· Sustituye "Enter Name:" por "Please enter your username:".
· Sustituye "Enter Password:" por "Please enter your password:".
- Crea dos _commits_, uno para cada modificación.

5. - Cambia en `src/AdminLogin.java` (línea 68) la contraseña del admin por ésta:
a74R#H0LarT5%x
- Crea un _commit_ con el cambio.
- Te llega una corrección por email. La contraseña no es la que habías puesto, es:
cYZxU!4Asr*LR3Nf
- Corrige la contraseña y modifica el _commit_ anterior, sin crear un _commit_ más en el log.

- **¿Qué comando has usado para hacer el punto anterior?**

6. - En `src/BooksForm.java`, cambia "books" por "book" en todas las strings en las que aparezca (sólo en las strings, no tienes que cambiar ningún nombre de variable).
- Crea un _commit_ con la modificación.

7. - Abre los tres archivos `.sql` y cambia el engine de las tablas, de InnoDB a MyISAM.
- Crea un _commit_ para cada archivo (te deben quedar tres _commit_s).
- Te has arrepentido: ahora crees que sería mejor que estuviera todo en un solo _commit_. Haz los pasos necesarios para que tu rama temporal tenga un solo _commit_, sin tocar nada del código de los archivos.
- **¿Qué comandos has usado para conseguir el punto anterior?**

8. - Vuelven a pedirte que cambies la contraseña del admin (`src/AdminLogin.java`, línea 68) por esta otra: uV2?bbX4[3hFw
- Crea un _commit_ con el cambio

9. - Mueve HEAD hasta el _commit_ que creaste en el punto 5 y comprueba que los archivos .sql tenían aún las tablas con ENGINE=InnoDB (lo cambiaste dos puntos después).
- Ahora vuelve a mover HEAD al _commit_ en el que estabas.
- **¿Qué comando has lanzado para hacer esto último?**
- En `src/DeleteLibrarian.java`, cambia el nombre de la variable lblEnterId por lblEnterLibrarianId (en todas las líneas donde aparezca).
- Crea un _commit_ con el cambio.

10. - En `src/DeleteLibrarian.java`, sustituye el label "Enter Id:" por "Enter labririan Id:" (la errata es adrede) y modifica el tamaño de letra del botón de borrar a 15 (sustituye el 13 de la línea 70 por un 15).
- Crea dos _commits_ con ambas modificaciones.
- No integres aún esta rama. Déjala como está, vuelve a develop y continúa con la
siguiente tarea.

11. - Tienes que hacer que el repositorio ignore la carpeta `.settings` y el archivo `.project`, pero como ya están siendo versionados, necesitas primero desversionarlos.
- Una vez desversionados (sacados del repositorio local), haz que el repositorio los ignore.
- Crea un _commit_ con los cambios.
- **¿Qué comandos has lanzado para los dos puntos anteriores?**

12. - Haz esta tarea sin crear una rama temporal (vamos a simular un error), crearás el _commit_ en develop.
- En `src/LibrarianSuccess.java`, sustituye el texto del botón "Return book" por "Return a book".
- Crea un _commit_ con el cambio.
- Te das cuenta de que has hecho el _commit_ en develop, cuando tenías que haber creado una nueva rama para ello y haber hecho el _commit_ ahí. Da los pasos necesarios para corregir el error. Pista: te será útil dibujar en un papel cómo ha quedado el log en cuanto a forma, _commits_ y “carteles” de ramas, y al lado dibujar cómo tendría que haber quedado todo si lo hubieras hecho bien.
- **¿Qué comandos has lanzado para resolver el error?**

13. - Te piden que vuelvas a dejar la contraseña del admin como la que metiste en el punto 5. Teniendo en cuenta que ya tienes el cambio registrado en un _commit_, **¿qué harías para volver a poner esa contraseña sin tocar el código?** Pista: lo que quieres hacer es aplicar en tu rama los cambios de un _commit_ aislado.
- Te tendrá que quedar un _commit_ nuevo, y cabe la posibilidad de que tengas que
resolver algún conflicto.

14. - En `src/DeleteLibrarian.java`, sustituye el label "Enter Id:" por "Enter librarian Id:" (esta vez sin errata).
- Crea un _commit_ con el cambio.

15. - Para esta tarea no tienes que crear ninguna rama temporal.
- Vuelve a la rama del punto 10, donde introdujiste la errata. Vamos a integrarla ahora en develop (recuerda hacerlo mediante _Pull Request_, como las otras). Al visualizar la PR, te debería avisar de que va a haber un conflicto al mergear.
- Resuelve el conflicto en tu máquina. Recuerda que no puedes añadir nuevos _commit_s a develop en local, porque luego no la podrás subir al servidor.

16. - En `src/LibrarianSuccess.java`, sustituye la etiqueta "View Books" por "View All Books".
- Crea un _commit_ con la modificación.
- Crea en el _commit_ una etiqueta anotada. Llámala ‘v1.1.0’ y en el mensaje escribe “Release con fixes de texto, tamaños de fuentes y motor tablas MySQL”.
- Asegúrate de que la etiqueta se sube al repositorio remoto cuando subas la rama.

17. - Tanto en local como en remoto sólo deberían quedar las ramas _main_ y _develop_.
- **Describe las acciones que has realizado y/o comandos que has lanzado para comprobarlo, y para borrar las ramas que se te hubieran quedado colgadas durante el ejercicio**
