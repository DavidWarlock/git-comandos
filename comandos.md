# Comandos Git

(Mostrar version de git, el — se refiere a que viene una palabra completa)

```bash
git —version
```

(Un solo - se refiere a abreviatura)

```bash
git commit -am 
```

```bash
git config —global init.defaultBranch <name>
```

Soluciona error mensaje con CRLF al hacer commit

```bash
git config core.autocrlf true
```

Reinicia  el proyecto al estado del ultimo commit

```bash
git checkout -- .
```

Commit y añadir el archivo en un solo comando (Solo archivos trackeados)

```bash
git commit -am ""
```

```bash
git log
```

Los cambios en el stage prevalecen si se le hace otro cambio y se hace un reset al archivo.

Por defecto Git no da seguimiento a directorios vacíos, debe añadirse dentro un archivo con el nombre .gitkeep

```bash
git status --short
```

Crear un alias

```bash
git config --global alias.s "git status --short"
```

Cambiar manualmente la configuración

```bash
git config --global -e
```

Corregir el mensaje del último commit

```bash
git commit --amend -m "Nuevo mensaje"
```

**Soft**

*"Elimina" los commits posteriores al commit al que estas haciendo el reset*

*Conserva los cambios en el stage area*

*Conserva los cambios que tengas en tus archivos (working directory)*

```bash
git reset --soft [HEAD^, hash]
git add .
git commit -m "Nuevo mensaje"
```

**Mixed**

*"Elimina" los commits posteriores al commit al que estas haciendo el reset*

*Deshace los cambios en el stage area*

*Conserva los cambios que tengas en tus archivos (working directory)*

```bash
git reset --mixed [hash]
```

**Hard**

*"Elimina" los commits posteriores al commit al que estas haciendo el reset*

*Deshace los cambios en el stage area*

*Deshace los cambios que tengas en tus archivos (working directory)*

```bash
git reset --hard [hash]
```

Ver log de todos los cambios realizados

```bash
git reflog
```

Crear tag sobre el último commit

```bash
git tag [nombre-del-tag]

// Eliminar tag
git tag -d [nombre-del-tag]
```

Crear tag con versión

```bash
git tag -a [v1.0.0] -m "Descripcion de versión 1.0.0"

//Crear tag sobre un commit especifico
git tag -a [v1.0.0] [7ab4912c/Hash] -m "Descripcion de versión 1.0.0"
```

Agregar cambios al stash

```bash
git stash
```

Mostrar listado de stashes

```bash
git stash list
```

Aplicar último stash

```bash
git stash pop
```

Eliminar último stash

```bash
git stash drop
```

Aplicar stash especifico

```bash
git stash apply stash@{0}
```

Guardar stash con mensaje

```bash
git stash save "Mensaje"
```

> **Nota del autor:** Evitar utilizar rebase cuando los cambios ya esten en remoto
> 

Hacer un rebase para actualizar rama (mandar los cambios de un commit despues del ultimo commit o el commit seleccionado de otra rama)

```bash
git checkout rama-cambios
git rebase master
git checkout master
git merge rama-cambios
```

Hacer un rebase interactivo para modificar commits

```bash
git rebase -i HEAD~4 (o numero de commits detrás del último)
```

Agregar url de origen remoto

> Se pueden tener varios remotes en un mismo repositorio
> 

```bash
git remote add [origin/nombreRemoto/etc] https://origen....
```

Ver remoto configurado

```bash
git remote -v
```

Enviar repositorio local al remoto (push)

```bash
git push -u [origin/nombreRemoto/etc] [master/main/rama]
# **-u:** Establece master por defecto y en el siguiente 
#     push no necesitamos especificar la rama
```
