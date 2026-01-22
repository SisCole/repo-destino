# Repositorio DESTINO - Deployment

Este es el **repositorio DESTINO** donde el workflow modificará el archivo YAML.

## Contenido

- `deployment.yaml` - Archivo de deployment de Kubernetes que será modificado por el workflow

## Imagen Actual

La imagen actual en el deployment es: `myapp:v1.0.0`

Esta imagen será actualizada automáticamente por el workflow del repositorio origen.

## Inicializar este repositorio

```bash
cd repo-destino
git init
git add .
git commit -m "feat: agregar deployment inicial"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/poc-by-pass-deploy-DESTINO.git
git push -u origin main
```

## Branch Protection

Para probar el bypass, configura branch protection en este repositorio:

1. Settings > Branches > Branch protection rules
2. Agregar regla para `main`:
   - ✅ Require a pull request before merging
   - ✅ Restrict who can push to matching branches
3. Agregar el usuario (del PAT) a la bypass list

## Verificación

Después de ejecutar el workflow en el repositorio origen:
- Un nuevo commit aparecerá directamente en `main`
- El archivo `deployment.yaml` tendrá la nueva imagen
- El bypass habrá funcionado ✅
