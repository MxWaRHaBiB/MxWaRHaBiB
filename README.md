2.7 Fundamentos de Git - Alias de Git
Alias de Git
Antes de terminar este capítulo sobre fundamentos de Git, hay otro pequeño consejo que puede hacer que tu experiencia con Git sea más simple, sencilla y familiar: los alias. No volveremos a mencionarlos más adelante en este libro, ni supondremos que los has utilizado, pero probablemente deberías saber cómo utilizarlos.

Git no deduce automáticamente tu comando si lo tecleas parcialmente. Si no quieres teclear el nombre completo de cada comando de Git, puedes establecer fácilmente un alias para cada comando mediante git config. Aquí tienes algunos ejemplos que te pueden interesar:

$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
Esto significa que, por ejemplo, en lugar de teclear git commit, solo necesitas teclear git ci. A medida que uses Git, probablemente también utilizarás otros comandos con frecuencia; no dudes en crear nuevos alias para ellos.

Esta técnica también puede resultar útil para crear comandos que en tu opinión deberían existir. Por ejemplo, para corregir el problema de usabilidad que encontraste al quitar del área de preparación un archivo, puedes añadir tu propio alias a Git:

$ git config --global alias.unstage 'reset HEAD --'
Esto hace que los dos comandos siguientes sean equivalentes:

$ git unstage fileA
$ git reset HEAD fileA
Esto parece un poco más claro. También es frecuente añadir un comando last, de este modo:

$ git config --global alias.last 'log -1 HEAD'
De esta manera, puedes ver fácilmente cuál fue la última confirmación:

$ git last
commit 66938dae3329c7aebe598c2246a8e6af90d04646
Author: Josh Goebel <dreamer3@example.com>
Date:   Tue Aug 26 19:48:51 2008 +0800

    test for current head

    Signed-off-by: Scott Chacon <schacon@example.com>
Como puedes ver, Git simplemente sustituye el nuevo comando por lo que sea que hayas puesto en el alias. Sin embargo, quizás quieras ejecutar un comando externo en lugar de un subcomando de Git. En ese caso, puedes comenzar el comando con un carácter !. Esto resulta útil si escribes tus propias herramientas para trabajar con un repositorio de Git. Podemos demostrarlo creando el alias git visual para ejecutar gitk:

$ git config --global alias.visual "!gitk"

<!---
MxWaRHaBiB/MxWaRHaBiB is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
