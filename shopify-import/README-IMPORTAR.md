# 🛠️ Cómo crear la tienda SELVÁ con estos archivos (Shopify + Dropi + contraentrega)

Sigue los pasos en orden. La mayoría es **importar / copiar-pegar**.

---

## Paso 0 — Crear la cuenta y lo básico
1. Crea la tienda en **shopify.com** (prueba gratis → plan Basic).
2. **Configuración → General:** país Colombia, moneda **COP**, zona horaria Bogotá.
3. **Configuración → Idiomas:** Español.
4. Sube **logo** y define **marca/colores** (ver `config/marca-colores-fuentes.md`).

## Paso 1 — Instalar el tema y pegar las plantillas
1. **Online Store → Themes →** añade el tema **Dawn** (gratis) → *Edit code*.
2. Abre `templates/index.json` y **reemplaza** su contenido por el de `templates/index.json` de esta carpeta.
3. Abre `templates/product.json` y reemplázalo por el de aquí.
4. En `snippets/` crea **`selva-trust-badges.liquid`** y pega el de esta carpeta.
   > Esto hace que el botón de compra muestre los sellos de confianza.
5. Guarda. Revisa la vista previa.

> ⚠️ Las plantillas asumen handles de producto como `serum-glow-vitamina-c`. Si tus productos de Dropi tienen otro handle, ajústalo en la sección *featured-product* del `index.json`.

## Paso 2 — Cargar productos (2 opciones)
**Opción A — Dropi (recomendada, con contraentrega):**
1. Instala la app **Dropify – Import products from Dropi and Sync Orders** (apps.shopify.com/dropify-5).
2. Conéctala a tu cuenta **Dropi** (token de acceso).
3. Busca productos de **belleza / cuidado de la piel**, impórtalos a Shopify (trae imágenes, precio sugerido y stock).
4. Edita títulos/descripciones/SEO usando el copy de `products.csv` y de las Fases 4-5.
   > Cuando entre una venta, Dropify crea la orden en Dropi y **Dropi despacha y cobra el contraentrega**.

**Opción B — CSV (marca propia o productos directos):**
1. **Online Store → Products → Import →** sube `products.csv`.
2. Añade imágenes a cada producto (Dropi o tu fotografía).
3. Revisa precios/márgenes.

## Paso 3 — Páginas (legales + FAQ + contacto)
1. **Online Store → Pages → Add page** por cada una.
2. Pulsa `<>` (Show HTML) y pega el bloque correspondiente de `paginas-html/paginas.html`.
3. Crea: privacidad, terminos, devoluciones, envios, contacto, preguntas-frecuentes, seguimiento.

## Paso 4 — Menús
1. **Online Store → Navigation → Main menu:** Inicio · Catálogo · Ofertas · Sérum Glow · Kit Esencial · FAQ · Contacto · Seguir mi pedido.
2. **Footer menu:** FAQ · Contacto · Seguimiento · Envíos · Devoluciones · Privacidad · Términos.

## Paso 5 — Pagos
1. **Configuración → Pagos → Mercado Pago** (ya lo tienes): activa **tarjeta + PSE**.
2. **Contraentrega:** activa el método manual **"Pago contra entrega (efectivo)"** en *Configuración → Pagos → Métodos de pago manuales*, **y/o** instala una app de formulario COD:
   - **Releasit COD Form & Upsell** o **COD King** → botón "Pagar al recibir" + **verificación por WhatsApp (OTP)** para evitar pedidos falsos.
3. (Recomendado) Ofrece **-5% por pago anticipado** para convertir COD en prepago.

## Paso 6 — Envíos e impuestos
1. **Configuración → Envíos:** crea tarifa Colombia + **Envío GRATIS desde $120.000** (tarifa por precio).
2. **Configuración → Impuestos:** IVA Colombia (19% donde aplique), precios con IVA incluido.

## Paso 7 — Apps clave
- Reseñas: **Judge.me** (estrellas + nº de reseñas).
- Email/automatización: **Klaviyo** (pop-up -10% + carrito abandonado).
- Tracking: **AfterShip** (página "Seguir mi pedido").
- COD: **Releasit/COD King** (ver Paso 5).
- Analítica: **Microsoft Clarity** (gratis).

## Paso 8 — Antes de lanzar (checklist)
- [ ] Compra de prueba en **móvil** con tarjeta y con **contraentrega**.
- [ ] Sellos de confianza visibles sobre el botón de compra.
- [ ] Envío gratis > $120.000 funcionando.
- [ ] Páginas legales publicadas y enlazadas en el footer.
- [ ] Pixel de Meta/TikTok y GA4 disparando eventos.
- [ ] Dominio `selva.co` conectado.

---

### Archivos de esta carpeta
| Archivo | Para qué |
|---|---|
| `products.csv` | Importar 4 productos SELVÁ (copy + SEO listos) |
| `templates/index.json` | Estructura de la Home (Dawn) |
| `templates/product.json` | Estructura de la página de producto (Dawn) |
| `snippets/selva-trust-badges.liquid` | Sellos de confianza sobre el botón |
| `config/marca-colores-fuentes.md` | Colores y tipografías a configurar |
| `paginas-html/paginas.html` | HTML de páginas legales + FAQ + contacto |


---

## Extra A — Upsell de carrito + barra de envío gratis
Archivo: `snippets/selva-cart-upsell.liquid`
1. En *Edit code* crea `snippets/selva-cart-upsell.liquid` y pega el contenido.
2. Agrega `{% render 'selva-cart-upsell' %}` dentro de **`sections/cart-drawer.liquid`** y de **`sections/main-cart-footer.liquid`** (cerca del subtotal).
3. Ajusta dentro del snippet: `umbral` (centavos; $120.000 = 12000000) y `upsell_handle` (producto complementario).
> Muestra "Te faltan $X para envío gratis" + un producto para agregar en 1 clic (sube el ticket).

## Extra B — Página de Quiz de tipo de piel
Archivo: `paginas-html/quiz-tipo-piel.html`
1. **Pages → Add page** "Descubre tu rutina" (handle `quiz`).
2. Pulsa `<>` (Show HTML) y pega todo el archivo.
3. (Opcional) Conecta el formulario de correo a **Klaviyo** donde dice `=== CONECTAR A KLAVIYO ===`.
4. Enlaza el quiz desde el menú y los botones "Hacer el quiz" del Home.

## Extra C — Marketing (en la carpeta `../marketing/`)
- `anuncios-meta-tiktok.md`: 5 guiones + ganchos + estructura de campaña.
- `flujo-carrito-abandonado-klaviyo.md`: flujos de email/WhatsApp (carrito, bienvenida, post-compra, recompra).
