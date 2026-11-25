# inventario-scan

Página para hacer el inventario de la tienda con el móvil: leer códigos de barras o hacer fotos de las estanterías,
y guardarlo todo en la carpeta de Dropbox de cada estantería. Sin iniciar sesión (buzón de la tienda), o con
Dropbox o Google Drive.

**Abrir en el móvil:** https://verasia-administration.github.io/inventario-scan/

## Cómo se usa

1. La primera vez:
   - **Buzón de la tienda (sin cuenta):** abrir en el móvil el enlace o el QR que da la tienda (solo una vez) y poner
     un nombre corto para el móvil. Lo registrado va al buzón y el PC de la tienda lo pasa a Dropbox (cada 15 minutos).
   - O con cuenta: «Conectar con Dropbox» o «Conectar con Google Drive».
   Con el buzón y con Google Drive se pone un nombre corto para el móvil (la app le añade 4 caracteres al azar).
2. Elegir el idioma (Chino / Coreano / Japonés) y el destino (la estantería, o Papelería / Objetos en japonés).
3. Elegir el archivo: uno nuevo (`<destino>_AAAA-MM-DD.csv`) o seguir con uno que ya exista.
4. Modos:
   - **A · 1 = 1**: apunta al código y pulsa «Registrar» (cantidad 1).
   - **B · Cantidad**: al leer un código se pide la cantidad.
   - **C · Foto**: foto de la estantería o de la sección.
5. «Anular última» borra la última lectura del archivo.

Sin conexión sale un aviso rojo: lo que se registre se guarda en el móvil y se envía solo al volver la conexión.
Con Google Drive, el permiso dura ~1 hora: cuando caduca sale «Reconectar Google» (lo registrado no se pierde).

## Qué se guarda y dónde

- Nada se guarda en este repositorio ni en GitHub. Todo va a la carpeta del destino:
  - Dropbox: `<destino>_AAAA-MM-DD.csv` (`fecha_hora;codigo;cantidad`), `<nombre>_resumen.csv` y las fotos
    `<destino>_AAAA-MM-DD_HH-MM-SS.jpg`.
  - Buzón: lo mismo que Dropbox (el PC de la tienda escribe el CSV con las lecturas de todos los móviles, el resumen y
    las fotos). Si el CSV ya lo había escrito otro (p. ej. un móvil con Dropbox), las del buzón van a `<nombre>_buzon.csv`.
  - Google Drive: un CSV por móvil, `<destino>_AAAA-MM-DD_<móvil>.csv`; el resumen `<destino>_AAAA-MM-DD_resumen.csv`
    suma los de todos los móviles; fotos `<destino>_AAAA-MM-DD_HH-MM-SS_<móvil>.jpg`.
- Cada móvil guarda en su navegador su acceso y lo que aún no se ha enviado.
- La App key de Dropbox, el ID de cliente de Google y la dirección del buzón que aparecen en `index.html` no son
  secretos. La clave del buzón sí lo es: no está aquí; llega a cada móvil con el enlace o el QR de la tienda.

## Mantenimiento

La configuración (App key, ID de cliente de Google, dirección del buzón, rutas e ids de las carpetas) está al principio de `index.html`.
El código, las pruebas y los documentos del proyecto están en el repositorio interno de AJH
(`proyectos/inventario-scan`); este repositorio solo contiene lo que se publica. No lo edites aquí directamente.
