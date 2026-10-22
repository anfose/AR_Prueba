[LEEME.md](https://github.com/user-attachments/files/33798299/LEEME.md)
# Plantilla WebAR · Historia en escenas

Experiencia de realidad aumentada que se abre desde el navegador del celular (Android o iPhone), sin instalar ninguna app. Al apuntar la cámara al marcador impreso aparece contenido 3D. El estudiante avanza la historia escena por escena con los botones, y cada escena lleva un subtítulo.

Tecnología: A-Frame 1.6.0 + AR.js 3.4.8, ambos gratuitos y de código abierto.

## Archivos

- `index.html`: la experiencia completa. Es el único archivo que hay que editar.
- `marcador-hiro.png`: el marcador. Imprímelo en papel blanco, idealmente de 8 cm o más, o muéstralo en otra pantalla.

## Cómo personalizarla

Abre `index.html` en cualquier editor de texto y busca **"EDITA AQUÍ"**.

1. **Texto de cada escena:** cambia el contenido de `data-subtitulo="..."`.
2. **Contenido 3D:** reemplaza las figuras de ejemplo (`a-box`, `a-sphere`…) por imágenes, videos o modelos 3D. Hay ejemplos listos para copiar al final del bloque del marcador.
3. **Más o menos escenas:** copia o borra un bloque `<a-entity class="escena">` completo. El contador se ajusta solo.
4. **Archivos propios** (fotos, .mp4, .glb): ponlos en la misma carpeta y declara cada uno en `<a-assets>`.

Medidas: 1 unidad equivale al ancho del marcador. `position="0 0.5 0"` significa media unidad por encima del papel.

## Cómo publicarla gratis (GitHub Pages)

La cámara del celular solo funciona en páginas con HTTPS. GitHub Pages lo da sin costo.

1. Crea una cuenta en github.com y un repositorio público nuevo.
2. Sube `index.html`, `marcador-hiro.png` y tus recursos con *Add file → Upload files*.
3. Ve a *Settings → Pages*, elige la rama `main` y la carpeta `/ (root)`, y guarda.
4. En uno o dos minutos la experiencia queda publicada en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/`.
5. Convierte esa dirección en un código QR para compartirla.

## Limitaciones que conviene conocer

- **Rastreo por marcador:** el contenido solo aparece mientras la cámara ve el marcador. No reconoce superficies como el piso o una mesa. Para eso hace falta WebXR, que en iPhone no funciona en Safari.
- **Luz y tamaño:** el marcador necesita buena iluminación y su borde negro debe verse completo.
- **Texto 3D (`a-text`):** la fuente por defecto no muestra bien tildes ni ñ. Pon los textos en español en el subtítulo.
- **Videos en iPhone:** deben llevar `muted playsinline` y empiezan a reproducirse cuando la persona toca un botón.
- **Modelos 3D:** procura que pesen menos de 5 MB cada uno, porque la página se descarga por datos móviles.
- **Marcadores propios:** se pueden crear con el generador de AR.js (*AR.js Marker Training*). Hay que cambiar `preset="hiro"` por `type="pattern" url="mi-marcador.patt"`.
