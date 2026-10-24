# Configuración pendiente: publicación automática segura

## Qué cambia esta iteración
- Se retiraron las instrucciones de GitHub visibles para el usuario final.
- El panel presenta acciones de Vista previa, Guardar borrador y Publicar cambios.
- El botón Publicar intenta llamar a un servicio de publicación configurado en `data/cms-config.json`.
- No se expone ningún token de GitHub en HTML/JavaScript.

## Importante
Esta entrega mejora la interfaz, pero la publicación automática no queda operativa solo por subir estos archivos. `data/cms-config.json` tiene `publishEndpoint` vacío a propósito. No se debe colocar un token en este archivo.

Para activar publicación real se necesita desplegar un backend (por ejemplo, Cloudflare Worker) que:
1. Autentique al usuario y valide su rol del lado servidor.
2. Reciba y valide el contenido de `nosotros`.
3. Guarde la actualización en GitHub mediante un token almacenado como secreto del backend.
4. Permita únicamente las rutas y operaciones autorizadas.
5. Registre quién publicó y cuándo.
6. Proteja el endpoint contra solicitudes no autorizadas y abuso.

Antes de habilitarlo para usuarios finales, integrar autenticación/roles reales. GitHub Pages por sí solo no proporciona backend ni autorización editorial.
