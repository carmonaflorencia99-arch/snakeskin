# SnakeSkin Lash Studio — Web

Web de SnakeSkin, estudio privado de extensiones de pestañas en Mendoza.
Estética negro + cromo + violeta neón, con la muñeca 3D de SnakeSkin en la portada.

## Estructura

```
index.html          Página completa (estilos y scripts incluidos)
doll-model.js       Modelo 3D de la muñeca (GLB embebido en base64)
media/              Videos y portadas (intro del logo, turno, Lyra, maquillaje)
docs/               Guía de estética para flyers, posts e historias
```

## Cómo verla en tu compu

Por usar módulos de JavaScript, la página necesita abrirse desde un servidor local (no con doble clic):

```bash
npx serve .
# o
python3 -m http.server 8080
```

Después abrí http://localhost:8080 (o el puerto que indique).

## Publicar en Vercel

1. En vercel.com → **Add New → Project**.
2. Importá este repo (`snakeskin`).
3. Framework preset: **Other**. No hace falta build command ni output directory.
4. **Deploy.** Cada cambio que se suba a `main` se publica solo.

## Videos y CDN

Vercel sirve todo desde su CDN global (Edge Network). `vercel.json` marca `media/` y el modelo 3D como caché de 1 año, así las visitas repetidas no vuelven a descargar nada.
Cada video tiene dos calidades: `*-hd.mp4` (720p vertical / 1080p horizontal) y una liviana. La página elige HD en conexiones rápidas y la liviana con datos lentos o ahorro de datos.

## Tecnologías

- [three.js](https://threejs.org/) 0.160 (desde jsDelivr) para el 3D, postprocesado bloom y carga del modelo GLB.
- Google Fonts: Michroma (títulos) y Manrope (textos).
- Sin frameworks ni build: HTML, CSS y JS puros.

## Dominio

www.snakeskinlash.com → en Vercel: Project → Settings → Domains → agregar el dominio y copiar los registros DNS que indique en el proveedor donde se compró.

## Datos de contacto en la web

- Reservas online: https://snakeskinlashstudio.setmore.com/

- WhatsApp: +54 9 261 671-6742
- Instagram: [@snakeskin.lash](https://instagram.com/snakeskin.lash)
