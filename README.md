# 🧠 Comandos Git Útiles

Una recopilación rápida de comandos Git usados frecuentemente para desarrollo diario y flujos de ramas.

---

## 🔍 Ver ramas y commits

```bash
git branch                  # Ver ramas locales
git branch -r               # Ver ramas remotas
git branch -a               # Ver ramas locales y remotas
git branch -v               # Ver última referencia de cada rama local
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

## Fusionar y actualizar ramas

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

