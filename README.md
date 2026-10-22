# Plantilla WebAR · un marcador, un contenido

Al apuntar la cámara del celular al marcador impreso, sobre el papel aparece **un modelo 3D (.glb) o un video (.mp4)**. Todo vive en un repositorio de GitHub y se publica gratis con GitHub Pages. No hace falta instalar ninguna app ni pagar alojamiento.

## Qué hay en la carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La experiencia. Solo se edita el bloque **CONFIGURACIÓN** del inicio. |
| `generador.html` | Convierte una imagen en marcador. Entrega el `.patt` y el PNG para imprimir. |
| `marcador/` | El marcador en uso: `marcador.patt` y `marcador-imprimir.png`. |
| `ejemplos/` | Un modelo y un video de prueba. Se pueden borrar al poner los propios. |
| `datos/camera_para.dat` | Calibración de la cámara. No se toca. |

## Pasos para cada estudiante

1. **Crear su copia.** Entra al repositorio del curso y usa *Use this template → Create a new repository*. El repositorio debe ser público.
2. **Crear su marcador.** Abre `generador.html` en el computador y elige una imagen. Descarga los dos archivos y súbelos a la carpeta `marcador/` con estos nombres exactos, reemplazando los de ejemplo:
   - `marcador.patt`
   - `marcador-imprimir.png`
3. **Subir su contenido.** Sube el `.glb` o el `.mp4` con *Add file → Upload files*.
4. **Configurar.** Abre `index.html`, pulsa el lápiz (*Edit*) y cambia solo el bloque CONFIGURACIÓN:
   ```js
   titulo: 'Nombre de mi pieza',
   marcador: 'marcador/marcador.patt',
   tipo: 'video',              // 'modelo' o 'video'
   archivo: 'mi-video.mp4',    // nombre exacto del archivo subido, con su carpeta si la tiene
   escala: 1, altura: 0, giro: 0,
   ```
   Pulsa *Commit changes*.
5. **Publicar.** Ve a *Settings → Pages* y elige la rama `main` y la carpeta `/ (root)`. En uno o dos minutos la experiencia queda en `https://USUARIO.github.io/REPOSITORIO/`.
6. **Probar.** Imprime `marcador-imprimir.png` y abre la dirección en el celular.

Si algo falla al cargar, la página muestra un aviso en rojo con el nombre del archivo que no encontró.

## Preparar los archivos

**Video (.mp4)**
- Usa el códec H.264 y audio AAC. Es la combinación que funciona en iPhone y Android. HandBrake, por ejemplo, exporta así con sus perfiles web.
- Mantenlo corto y liviano: idealmente menos de 15 MB y a 720p como máximo.
- El video arranca en silencio, porque los celulares lo exigen. El botón "Activar sonido" lo enciende.
- Se acomoda solo a la proporción del video (horizontal, vertical o cuadrado), acostado sobre el marcador.

**Modelo 3D (.glb)**
- Debe ser un solo archivo `.glb` con las texturas incluidas. Los `.gltf` con archivos aparte o los `.obj` no sirven.
- Procura que pese menos de 5 MB.
- Si se ve gigante o diminuto, ajusta `escala`. Si queda hundido en el papel, sube `altura`.

**Marcador**
- Usa formas grandes en blanco y negro que no sean simétricas. El generador avisa si la imagen sirve mal.
- Imprímelo en papel mate y deja el borde blanco alrededor del cuadro negro. El cuadro negro debe medir 8 cm o más.

## Límites de GitHub que conviene conocer

- Cada archivo subido desde el navegador puede pesar **hasta 25 MB**.
- El sitio publicado puede ocupar hasta 1 GB, y hay un límite flexible de 100 GB de tráfico al mes. Para un curso sobra.
- Después de cada cambio, la publicación tarda uno o dos minutos en actualizarse. Si el celular sigue mostrando la versión anterior, recarga la página.

## Para el docente

En el repositorio original, activa *Settings → General → Template repository*. Así cada estudiante crea su copia con un clic y conserva toda la estructura.
