# Brixor · sitio público

Landing estática e independiente de Brixor. HTML y CSS, sin dependencias ni servicios de backend. Todos los enlaces de navegación permanecen dentro de la landing; no enlazar a la aplicación, inicio de sesión ni registro.

## Desarrollo

```sh
python -m http.server 8080 --directory public
```

## Publicación

GitHub Pages publica únicamente `public/`. El workflow manual `Publicar landing` recibe el SHA probado y la evidencia local. No hay CI por push ni PR. Para publicar: Actions → Publicar landing → Run workflow, indicando el SHA de main verificado y la evidencia de sus pruebas locales.

## Dominio

Después de publicar, en Settings → Pages → Custom domain guardar `brixor.cl`. En Cloudflare, crear cuatro registros A para `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, y un CNAME `www` a `brixor-japs.github.io`. Todos en DNS only (nube gris). Quitar solo los registros web que entren en conflicto, conservar MX/TXT de correo y verificación. Esperar propagación y activar Enforce HTTPS en Pages cuando esté disponible.

Google Workspace verifica la propiedad con el TXT que entrega su asistente. Sus registros MX habilitan el correo; publicar la web no los sustituye.
