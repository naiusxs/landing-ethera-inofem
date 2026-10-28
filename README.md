# Ethera · landing de Inofem

Landing estática basada en el manual de identidad 2026 y en la maqueta `MELENA E INOFEM.pdf` (página de Inofem): base beige `#fffcf0`,
Garamond (títulos) + Gilroy (texto), acento rosa, barra y lema arcoíris, y orbes de color difuminado como
fondo (WebGL). CSS plano + GSAP, **sin build**. Es la gemela de la landing de Melena de León (carpeta `landing ETHERA`): misma estructura, otros colores, copy e imágenes.

```
index.html     contenido y estructura (copy de MELENA E INOFEM.pdf)
css/site.css   todo el diseño (tokens al inicio de :root)
js/main.js     interacciones y animaciones (GSAP/ScrollTrigger)
js/scene.js    aura de color WebGL (fragment shader a baja resolución)
js/config.js   datos del cliente (checkout, WhatsApp, redes, píxel de Meta, popup)
fonts/         Garamond y Gilroy en woff2 (convertidas de los TTF de la marca)
assets/brand/  frasco, logos, degradado y orbe extraídos del manual y la maqueta
vendor/        gsap y ScrollTrigger locales (sin CDN)
```

Ver en local: `npm run serve` (los módulos ES no cargan desde `file://`).
Regenerar `vendor/` tras `npm i`: `npm run vendor`.

- Modo ligero automático (<=4 núcleos, <=4 GB, ahorro de datos o `?lite=1`): aura a menor resolución y 30 fps.
- Si WebGL no está disponible, la página funciona igual sin el aura.
- `prefers-reduced-motion` desactiva las animaciones y deja el aura estática.
- Los precios están en `index.html`; los botones de plan siguen en "Muy pronto" hasta que `config.js` tenga `checkoutUrl`.
