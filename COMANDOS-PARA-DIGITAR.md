Mis comandos de la práctica

1. Para ver el gráfico del repositorio
git log --oneline --graph --all --decorate
> Me muestra todo el historial como un gráfico con todas las ramas

2. Los dos padres de una fusión
git show --oneline -s 5239a23^1
> Me muestra la primera versión que se juntó al fusionar
git show --oneline -s 5239a23^2
> Me muestra la segunda versión que se juntó al fusionar

3. Inspeccionar el historial
git log --stat -1
> Qué archivos cambiaron en el último commit

git log --grep="sección" --oneline
> Busca commits que mencionen la palabra "sección"

git log -S "conflicto" --oneline
> Busca dónde se agregó o cambió la palabra "conflicto"

git log --oneline --author="Jimmy"
> Solo los commits que hice yo

git shortlog -sn HEAD
> Cuenta cuántos commits hizo cada persona

4. Quién escribió cada línea
findstr /n "header" index.html
> Encuentra en qué número de línea está la palabra "header"

git blame -L 28,28 index.html
> Me dice quién modificó cada línea del archivo

5. Comparar versiones
git show HEAD~3 --stat
> Qué cambió hace 3 commits

git diff HEAD~5 HEAD --stat
> Resumen de cambios entre hace 5 commits y ahora

git diff HEAD~5 HEAD -- index.html
> Cambios específicos en el archivo index.html

git diff origin/main main --stat
> Comparo mi trabajo con lo que está subido en GitHub

git show HEAD~10:index.html
> Cómo se veía el archivo en una versión anterior

6. El revert
git log --oneline -3
> Últimos 3 commits

git log --oneline --decorate -4
> Últimos 4 commits con sus etiquetas

7. Detached HEAD
git log --oneline HEAD~9 HEAD~8
> Compara dos commits específicos

8. Recuperar con reflog
git reflog -10
> Muestra todo lo que he hecho en Git, incluso si cambié de rama o borré algo

9. Etiquetas y ramas
git tag
> Lista mis etiquetas

git log --oneline --decorate -4
> Últimos commits con etiquetas

git branch -v
> Todas las ramas con su último commit

git branch -a
> Ramas locales y las que están en GitHub

git branch --show-current
> En qué rama estoy ahora

10. Las 5 respuestas finales
(git log --grep="sección" --oneline | Measure-Object -Line).Lines
> Cuenta cuántos commits mencionan "sección"

git log -S "conflicto" --oneline --reverse
> El primer commit que mencionó "conflicto"

git blame -L 28,28 index.html
> Quién escribió esa línea del encabezado

(git show HEAD~10:index.html | Select-String "<section>" | Measure-Object -Line).Lines
> Cuántas secciones había en una versión anterior del archivo

git log --oneline origin/main..main
> Si tengo cambios que no he subido a GitHub todavía