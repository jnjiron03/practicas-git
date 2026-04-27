# Recuperación del archivo errores.sh

## Situación

El archivo `errores.sh` fue eliminado accidentalmente del directorio de trabajo.

## Proceso de recuperación

### 1. Verificación del estado

Con `git status` comprobamos que Git detecta la eliminación del archivo,
apareciendo como *deleted* en rojo.

### 2. Consulta del historial

Con `git log --oneline` obtenemos el listado de commits y localizamos
el hash del commit que introdujo el archivo (`d102e4b`).

### 3. Restauración del archivo

```bash
git restore --source=d102e4b errores.sh
```

Se usa `git restore --source=<hash>` para recuperar el archivo directamente
desde un commit específico sin mover HEAD ni alterar el historial.
El archivo queda restaurado exactamente como estaba en ese commit.

## Comandos utilizados

```bash
rm errores.sh
git status
git log --oneline
git restore --source=d102e4b errores.sh
ls -la
```
