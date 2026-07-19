# AR para tu libro — 100% gratis, sin límite de escaneos

Tecnología: **MindAR.js** (open source) + **GitHub Pages** (hosting gratis). Sin límites de vistas, marcadores ni vídeos.

## Pasos

### 1. Fotografía cada página que llevará QR
- Foto plana, buena luz, sin reflejos, la página debe tener suficiente detalle visual (texto + alguna imagen ayuda al tracking).
- Formato JPG/PNG. Una foto por página (hasta 20).

### 2. Compila las imágenes en un único archivo `targets.mind`
1. Abre: https://hiukim.github.io/mind-ar-js-doc/tools/compile
2. Sube tus 20 imágenes **en el orden** que quieras (ese orden define el `targetIndex`: la primera es 0, la segunda 1, etc.).
3. Descarga `targets.mind` y colócalo en la carpeta `targets/`.

### 3. Prepara los vídeos
- Formato MP4 (H.264), ligero (ideal <15-20MB cada uno para que cargue rápido en móvil).
- Nómbralos `clip0.mp4`, `clip1.mp4`... según el mismo orden del paso 2, y ponlos en `videos/`.

### 4. Completa el `index.html`
- Ya incluye el patrón para 3 clips (0,1,2). Duplica el bloque `<video>` en `<a-assets>` y el bloque `<a-entity mindar-image-target>` para cada página nueva, hasta llegar a 19 (20 en total). Solo cambia el número.

### 5. Publícalo gratis en GitHub Pages
1. Crea una cuenta gratis en https://github.com si no tienes.
2. Crea un repositorio nuevo (público) y sube toda esta carpeta (`index.html`, `targets/`, `videos/`).
3. Ve a Settings → Pages → Source: selecciona la rama `main` y guarda.
4. En unos minutos tendrás una URL tipo `https://tuusuario.github.io/turepo/`.

### 6. Genera los QR
- Uno por página, cada uno apuntando a la misma URL (la app detecta sola qué página es).
- Puedes usar cualquier generador de QR gratuito (ej. qrcode-monkey.com) con esa URL.
- Imprime el QR en la página correspondiente del libro.

## Notas importantes
- El lector abre el QR → se abre el navegador → pide permiso de cámara → enfoca la página → aparece el vídeo encima.
- Funciona en iOS y Android sin instalar ninguna app.
- Si un vídeo no carga bien en móvil, comprímelo (HandBrake, gratis) a resolución 720p.
