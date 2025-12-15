# 🧠 Comandos Git Útiles

Una recopilación rápida de comandos Git usados frecuentemente para desarrollo diario y flujos de ramas.

---

## 🔍 Ver ramas y commits

```bash
git branch                  # Ver ramas locales
git branch -r               # Ver ramas remotas
git branch -a               # Ver ramas locales y remotas
git branch -v               # Ver última referencia de cada rama local
git branch -vv              # Ver ramas vinculadas a su remoto, si estan actualizadas o adelantadas

git log --oneline           # Ver historial de commits en una línea
git log -n 5 --oneline      # Ver los últimos 5 commits
git log origin/mi-rama..HEAD --oneline  # Ver commits locales no subidos
```

---

## Trabajando con ramas

```bash
git fetch origin                            # Traer cambios del remoto (sin mezclar)
git checkout -b nueva-rama                  # Crear nueva rama desde rama actual
git checkout -b nueva-rama base             # Crear nueva rama desde otra rama
git checkout -b local origin/remota         # Crear rama local basada en rama remota
git push -u origin nueva-rama               # Subir nueva rama y establecer tracking
```

---

## Fusionar y actualizar ramas

```bash
git checkout develop
git pull origin develop                     # Actualizar rama local
git merge master                            # Fusionar master en develop

```

## Reset y limpieza de commits

```bash
git reset HEAD~1                            # Quitar último commit (mantiene cambios)
git reset --hard HEAD~1                     # Quitar último commit y cambios
git stash                                   # Guardar temporalmente cambios locales
git stash pop                               # Recuperar cambios stasheados

```

## Ver cambios y archivos en commits

```bash
git show                                    # Ver último commit con detalles
git show --name-only <hash>                 # Ver archivos modificados en un commit
git diff-tree --no-commit-id --name-only -r <hash>  # Solo nombres de archivos modificados

```

## Ver relación con el remoto

```bash
git status                                  # Ver estado actual vs remoto
git remote -v                               # Ver URL del remoto
git remote show origin                      # Ver detalles del remoto y ramas trackeadas

```

## Información extra

```bash
git branch --show-current                   # Saber en qué rama estás
```

## 🧭 Configuración de Tracking entre Ramas

En Git, puedes vincular una rama local con una rama remota para poder usar `git pull` y `git push` sin tener que especificar el nombre remoto o de la rama cada vez. Aquí te mostramos cómo y cuándo usar las dos opciones más comunes:

---

### ✅ `git push -u origin mi-rama`

Usa esto cuando estás creando y subiendo una **nueva rama** al remoto por primera vez:

```bash
git checkout -b mi-rama
git push -u origin mi-rama

```
### ✅ `git branch --set-upstream-to=origin/otra-rama`

git checkout hotfix
git branch --set-upstream-to=origin/develop


## 📌 Flujo típico: modificar → agregar → commitear → enviar

Cuando haces cambios en archivos dentro de tu repositorio, Git no los incluye automáticamente en el commit. Debes seguir este flujo:

---

### 1 Ver el estado actual

```bash
git status
```
### 2 Agregar archivos al staging area
```
git add archivo1.cs carpeta/archivo2.js   # Agregar archivos específicos
git add .                                 # Agregar todos los archivos modificados y nuevos
```
### 3 Hacer el commit
```
git commit -m "Descripción clara de los cambios"
```
### 4 Subir los cambios al remoto
```
git push
```


## 🔍 Ver diferencias de archivos modificados

Git te permite comparar fácilmente los cambios realizados en tus archivos antes de confirmar (commit).

---

### ✅ Ver cambios **NO agregados al staging area**

```bash
git diff ruta/del/archivo
```
### ✅ Ver cambios que ya agregaste con git add

```bash
git diff --cached ruta/del/archivo


