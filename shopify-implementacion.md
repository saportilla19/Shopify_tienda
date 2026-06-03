# Guía de implementación en Shopify (Online Store 2.0)

> Tema base recomendado: **Dawn** (gratis, rápido, secciones nativas). Todo esto se monta desde el **Editor de temas** (arrastrar/soltar secciones) sin tocar código en su mayoría.

---

## 1. Configuración inicial de la tienda
1. **Crear tienda** → plan Basic. Idioma: Español (Colombia). Moneda: **COP**. Zona horaria: Bogotá.
2. **Dominio:** conectar `selva.co`.
3. **Impuestos:** configurar IVA Colombia (19% donde aplique) y mostrar **precios con IVA incluido**.
4. **Envíos:** zonas Colombia; tarifa estándar + **envío gratis desde $120.000** (Configuración → Envíos → "Tarifa basada en precio").
5. **Pagos:** activar pasarela (**Wompi/Mercado Pago/PayU**) con tarjeta + **PSE** + **Nequi**, y app de **contraentrega** (Rocketfy/Dropi).
6. **Checkout:** pedir teléfono (obligatorio para COD/WhatsApp), activar "checkout abandonado".
7. **Notificaciones:** personalizar correos con la marca; conectar WhatsApp.

## 2. Marca (Configuración → Marca / Editor de temas → Configuración)
```
Colores
  Primario / Botones:      #234334  (texto botón #F4EFE6)
  Secundario / Acento:     #C68B59
  Fondo general:           #F4EFE6
  Texto:                   #2B2B2B
Tipografía
  Titulares:  Fraunces (o Playfair Display)
  Cuerpo:     Inter (o Work Sans)
Logo: subir versión principal + favicon (gota-hoja)
```

## 3. Estructura de archivos del tema (referencia)
```
theme/
├─ layout/theme.liquid
├─ templates/
│  ├─ index.json            ← HOME (secciones en orden de Fase 3)
│  ├─ product.json          ← PDP
│  ├─ product.serum.json    ← plantilla PDP del héroe (opcional)
│  ├─ collection.json
│  ├─ cart.json
│  ├─ page.json / page.contact.json
│  └─ blog.json / article.json
├─ sections/  (image-banner, rich-text, featured-product, multicolumn,
│              collapsible-content [FAQ], slideshow, newsletter, etc.)
├─ snippets/  (trust-badges, product-rating, etc.)
├─ blocks/
└─ config/settings_data.json
```

## 4. HOME — orden de secciones (templates/index.json)
| Orden | Sección Dawn | Contenido (de fase-4-home.md) |
|---|---|---|
| 1 | Announcement bar | Envío gratis / contraentrega / prueba social |
| 2 | Header (sticky) | Logo + menú + buscador + carrito |
| 3 | Image banner | HERO: H1 + sub + 2 CTA + rating |
| 4 | Multicolumn (4) | Barra de confianza (trust bar) |
| 5 | Multicolumn (4) | Beneficios con ícono |
| 6 | Rich text / Image with text | Problema/Solución (3 pasos) |
| 7 | Featured product | Sérum Glow |
| 8 | Image with text / Custom | Oferta ancla — Kit Esencial (-29%) |
| 9 | App section (Judge.me) | Carrusel de reseñas / UGC |
| 10 | Image with text | Antes/después |
| 11 | Rich text (destacado) | Garantía 30 días |
| 12 | Collapsible content | FAQ |
| 13 | Email signup / Newsletter | Captura -10% |
| 14 | Footer | Menús + pagos + legal + redes |

## 5. Ejemplo de bloque de configuración (sección Image banner / Hero)
> JSON ilustrativo del tipo que Shopify genera en `templates/index.json`. Sirve de guía para llenar el editor.
```json
{
  "sections": {
    "hero": {
      "type": "image-banner",
      "settings": {
        "image_overlay_opacity": 20,
        "image_height": "large",
        "desktop_content_position": "middle-left",
        "show_text_box": true,
        "color_scheme": "scheme-cream"
      },
      "blocks": {
        "heading": { "type": "heading", "settings": { "heading": "Piel luminosa y uniforme en 4 semanas", "heading_size": "h0" } },
        "text":    { "type": "text", "settings": { "text": "Sérum Glow con Vitamina C 10% + Niacinamida. Formulado en Colombia." } },
        "button":  { "type": "buttons", "settings": { "button_label_1": "Comprar mi Sérum Glow", "button_link_1": "shopify://products/serum-glow-vitamina-c", "button_label_2": "Hacer el quiz", "button_link_2": "shopify://pages/quiz" } }
      },
      "block_order": ["heading", "text", "button"]
    }
  },
  "order": ["hero"]
}
```

## 6. Snippet de trust badges (snippets/trust-badges.liquid)
> Pégalo en `snippets/` y llámalo con `{% render 'trust-badges' %}` sobre y bajo el botón de compra.
```liquid
<ul class="selva-trust" role="list">
  <li>🔒 Pago 100% seguro</li>
  <li>💵 Paga al recibir</li>
  <li>🚚 Envío 24-72h</li>
  <li>↩ 30 días de garantía</li>
  <li>🧪 Registro INVIMA</li>
</ul>
<style>
  .selva-trust{display:flex;flex-wrap:wrap;gap:.75rem;justify-content:center;
    list-style:none;padding:.75rem 0;margin:0;font-size:.9rem;color:#234334}
  .selva-trust li{background:#F4EFE6;border:1px solid #7E9B6E33;border-radius:999px;padding:.35rem .7rem}
</style>
```

## 7. PDP — orden de bloques (templates/product.json)
1. Media gallery + título + rating + precio + variantes + **Add to cart** + `trust-badges` + urgencia
2. Upsell al Kit (app Rebuy o bloque enlazado)
3. Descripción de ventas (metafield/rich text)
4. Características/ingredientes (tabla)
5. Cómo usar
6. Comparativa
7. Reseñas (Judge.me)
8. Garantía + FAQ (collapsible)
9. Cross-sell (productos relacionados)
10. Sticky add-to-cart (ajuste del tema/app)

## 8. Navegación (Configuración → Navegación)
- **Menú principal:** Inicio · Catálogo (mega) · Ofertas · Sérum Glow · Kit Esencial · FAQ · Contacto · Seguir mi pedido
- **Menú de pie:** Tienda · Ayuda · Legal · Redes
- Ver detalle en [`fase-4-menu-y-legales.md`](./fase-4-menu-y-legales.md).

## 9. Productos y colecciones a crear
**Productos**
- Sérum Glow — Vitamina C 10% + Niacinamida ($89.000) — handle `serum-glow-vitamina-c`
- Hidratante con FPS 50 ($98.000) — `hidratante-fps-50`
- Gel limpiador suave ($79.000) — `gel-limpiador-suave`
- **Kit Esencial 3 Pasos** ($189.000) — `kit-esencial-3-pasos` (bundle)

**Colecciones**
- `serums`, `limpiadores`, `hidratantes`, `proteccion-solar`, `kits`, `ofertas`
- Colecciones por necesidad (manchas, luminosidad, hidratación, piel sensible) usando **tags**.

**Metadatos por producto:** copia de [`fase-5-seo.md`](./fase-5-seo.md) (título, descripción, URL/handle, alt text).

## 10. Páginas a crear (Online Store → Páginas)
- `preguntas-frecuentes`, `contacto`, `seguimiento`, `privacidad`, `terminos`, `devoluciones`, `envios`, `quiz`, `nosotros`.
- Contenido en [`fase-4-menu-y-legales.md`](./fase-4-menu-y-legales.md).

## 11. SEO técnico
- Activar `Organization` + `Product` schema (Judge.me añade `Review`/`AggregateRating`).
- Editar `robots.txt.liquid` solo si es necesario.
- Conectar **Google Search Console** + enviar sitemap.
- Instalar **GA4** + **Meta Pixel** + **TikTok Pixel** (vía canal de ventas o Google&YouTube/Meta apps).

## 12. Checklist final pre-lanzamiento
- [ ] Pagos en modo real (tarjeta, PSE, Nequi, contraentrega) probados con una compra de prueba
- [ ] Envío gratis > $120.000 funcionando
- [ ] Reseñas visibles con estrellas + conteo
- [ ] Trust badges sobre el CTA en PDP
- [ ] Pop-up -10% y flujo de carrito abandonado activos
- [ ] Páginas legales publicadas y enlazadas en el footer
- [ ] Velocidad: PageSpeed móvil ≥ 70, imágenes WebP
- [ ] Pixels disparando eventos (probar con depurador de Meta)
- [ ] Política y mensajes de WhatsApp configurados
- [ ] Prueba de compra completa en móvil (incluida contraentrega)
```
```
