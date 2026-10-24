# G&S Geociencia — primera iteración del CMS (GitHub-first)

## Qué incluye esta entrega
- Se conserva la estructura y navegación existentes.
- `data/nosotros.json` contiene el contenido inicial de la página Nosotros.
- `nosotros.html` carga los campos publicados desde ese JSON y mantiene el contenido HTML como respaldo.
- `admin-pagina-editar.html` incluye campos editables, vista previa, guardado local y descarga del JSON para publicar manualmente en GitHub.

## Probar localmente
1. Descomprime el ZIP.
2. Abre una terminal en la carpeta del proyecto.
3. Ejecuta `python -m http.server 8000`.
4. Visita `http://localhost:8000/admin-pagina-editar.html` para editar y `http://localhost:8000/nosotros.html` para comprobar la página pública.

No abras los HTML con `file://` para esta prueba: la carga del JSON usa `fetch`, que requiere servir los archivos por HTTP.

## Publicar cambios en GitHub Pages
1. Entra al panel y abre `admin-pagina-editar.html`.
2. Edita los campos y pulsa **Descargar para publicar**.
3. En el repositorio GitHub, abre la carpeta `data`.
4. Reemplaza `nosotros.json` por el archivo descargado (mantén exactamente el nombre y la ruta).
5. Confirma el cambio con un commit.
6. Espera a que GitHub Pages termine el despliegue y verifica `nosotros.html`.

## Limitaciones de esta primera iteración
- El borrador se guarda solo en el navegador local y no se comparte entre administradores.
- La descarga de JSON no publica automáticamente en GitHub.
- Esta página no implementa autenticación ni autorización reales. No debe considerarse un CMS multiusuario seguro hasta incorporar un mecanismo de identidad y permisos del lado servidor.
- El contenido en `data/nosotros.json` es público porque lo consume el sitio público. No almacenar contraseñas, tokens ni información confidencial allí.
- Los textos de visión y valores, así como las fotografías, siguen marcados como pendientes cuando corresponde; deben ser confirmados por G&S antes de publicar.

## Siguiente paso
Validar esta edición de Nosotros en GitHub Pages. Después, reutilizar el patrón para el resto de módulos manteniendo todas las pantallas existentes y definir una solución segura para autenticación, roles y publicación multiusuario.
