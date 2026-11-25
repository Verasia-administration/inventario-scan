# inventario-scan

Página para hacer el inventario de la tienda con el móvil: leer códigos de barras o hacer fotos de las estanterías,
y guardarlo todo en el Dropbox de la tienda, en la carpeta de cada estantería.

**Abrir en el móvil:** https://verasia-administration.github.io/inventario-scan/

## Cómo se usa

1. La primera vez, «Conectar con Dropbox» (una vez por móvil).
2. Elegir el idioma (Chino / Coreano / Japonés) y el destino (la estantería, o Papelería / Objetos en japonés).
3. Elegir el archivo: uno nuevo (`<destino>_AAAA-MM-DD.csv`) o seguir con uno que ya exista.
4. Modos:
   - **A · 1 = 1**: apunta al código y pulsa «Registrar» (cantidad 1).
   - **B · Cantidad**: al leer un código se pide la cantidad.
   - **C · Foto**: foto de la estantería o de la sección.
5. «Anular última» borra la última lectura del archivo.

Sin conexión sale un aviso rojo: lo que se registre se guarda en el móvil y se envía solo al volver la conexión.

## Qué se guarda y dónde

- Nada se guarda en este repositorio ni en GitHub. Todo va al Dropbox de la tienda, dentro de la carpeta del destino:
  `<destino>_AAAA-MM-DD.csv` (`fecha_hora;codigo;cantidad`), `<nombre>_resumen.csv` y las fotos
  `<destino>_AAAA-MM-DD_HH-MM-SS.jpg`.
- Cada móvil guarda en su navegador su acceso a Dropbox y lo que aún no se ha enviado.
- La App key de Dropbox que aparece en `index.html` no es secreta.

## Mantenimiento

La configuración (App key y rutas de las carpetas de Dropbox) está al principio de `index.html`.
El código, las pruebas y los documentos del proyecto están en el repositorio interno de AJH
(`proyectos/inventario-scan`); este repositorio solo contiene lo que se publica. No lo edites aquí directamente.
