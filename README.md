# Control de Pedidos y Retiros — Saraza / Peña

App para cargar pedidos y retiros a mano y ver el pendiente por producto
calculado solo. Los datos viven en una planilla de Google Sheets propia
(no depende de Claude ni de ningún otro servicio de pago).

Planilla con los datos: https://docs.google.com/spreadsheets/d/1_EOj3Ffze7s915nQPtrBDffD0A9gV5abeUNcmlyGdRI/edit

## Cómo queda armado

- `index.html` — la app (una sola página, sin dependencias externas más
  que las tipografías de Google Fonts).
- `config.js` — acá va pegada la URL del Apps Script que conecta la
  página con la planilla.
- `apps-script/Code.gs` — el código que hay que pegar en el editor de
  Apps Script de la planilla (Extensiones → Apps Script). Trae los pasos
  de instalación como comentario arriba del todo.

## Puesta en marcha (una sola vez)

1. Abrí la planilla del link de arriba.
2. Extensiones → Apps Script.
3. Pegá el contenido de `apps-script/Code.gs` en el editor (reemplazando
   lo que haya).
4. Implementar → Nueva implementación → tipo "Aplicación web".
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier usuario**
5. Autorizá los permisos (es tu propia cuenta y tu propia planilla).
6. Copiá la URL que te da, termina en `/exec`.
7. Pegala en `config.js`, en `SHEETS_WEBAPP_URL`.
8. Si el repo tiene GitHub Pages activado, la página va a quedar andando
   sola en la URL de Pages del repo. Si no, activalo en
   Settings → Pages → Source: Deploy from a branch → main / (root).

Si en algún momento cambiás el código de Apps Script, tenés que hacer
"Implementar → Administrar implementaciones → editar (lápiz) → Nueva
versión" para que el cambio se vea reflejado en la URL ya publicada.
