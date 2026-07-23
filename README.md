# IntegracionContinua

Proyecto simple de una página web estática desplegada automáticamente con GitHub Actions y Surge.sh.

## Estructura

- index.html: página principal del sitio.
- .github/workflows/main.yml: workflow que despliega la web al hacer push a la rama main.

## Requisitos

- Un repositorio en GitHub.
- Un dominio en Surge.sh, por ejemplo: `mi-dominio.surge.sh`.
- Dos secretos en GitHub:
  - `SURGE_TOKEN`
  - `SURGE_DOMAIN`

## Despliegue automático

El workflow se activa al hacer push a la rama main y ejecuta:

```bash
surge ./ ${{ secrets.SURGE_DOMAIN }} --token ${{ secrets.SURGE_TOKEN }}
```

## Pasos para terminar la publicación

1. Crear el repositorio remoto en GitHub.
2. Agregar los secretos `SURGE_TOKEN` y `SURGE_DOMAIN` en la configuración del repositorio.
3. Subir los cambios con:

```bash
git remote add origin https://github.com/LuisJorg/IntegracionContinua.git
git branch -M main
git push -u origin main
```

4. Confirmar que el workflow corra en la pestaña Actions de GitHub.
