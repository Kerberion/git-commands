# 🧠 Comandos Git Útiles

Una recopilación rápida de comandos Git usados frecuentemente para desarrollo diario y flujos de ramas.

---

## 🔍 Ver ramas y commits

```bash
git branch                   # Ver ramas locales
git branch -r               # Ver ramas remotas
git branch -a               # Ver ramas locales y remotas
git branch -v               # Ver última referencia de cada rama local
git log --oneline           # Ver historial de commits en una línea
git log -n 5 --oneline      # Ver los últimos 5 commits
git log origin/mi-rama..HEAD --oneline  # Ver commits locales no subidos
