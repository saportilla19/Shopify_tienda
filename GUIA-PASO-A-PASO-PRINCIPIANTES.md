# 👣 Guía paso a paso para principiantes — Tienda SELVÁ

> Para quien **nunca ha montado una tienda online**. Sigue las etapas en orden, sin afán (un fin de semana basta).

---

## 📖 Glosario rápido
- **Shopify:** la plataforma donde vive tu tienda (tu "local" en internet).
- **Tema:** el diseño de la tienda. Usaremos uno gratis: **Dawn**.
- **Dropi:** plataforma colombiana de productos **sin inventario**; ellos despachan y cobran el **contraentrega**.
- **Dropify:** app que conecta Dropi con Shopify.
- **Contraentrega (COD):** el cliente paga en efectivo al recibir.
- **Mercado Pago:** pasarela para cobrar con tarjeta y PSE (ya lo tienes).

---

## ✅ ETAPA 0 — Antes de empezar (1 hora)
1. Un **correo** dedicado (ej: tienda.selva@gmail.com).
2. **Celular** para verificaciones.
3. **Cuenta bancaria** para recibir el dinero.
4. Marca: usaremos **SELVÁ** (nombre, colores y textos ya están en el repo).
5. (Recomendado) **RUT**; para validar puedes empezar como persona natural y formalizar una SAS al crecer. Consulta con un contador.

> 💡 Crea una carpeta "SELVÁ" en tu computador y guarda ahí todos tus usuarios y contraseñas.

---

## 🟢 ETAPA 1 — Crear la cuenta de Shopify (20 min)
1. Entra a **shopify.com → "Iniciar prueba gratis"**.
2. Correo + contraseña + nombre de la tienda ("SELVÁ").
3. Qué vendes → "Belleza / cuidado de la piel".
4. Ya estás en el **Panel (Admin)**, tu central de control.
5. **Configuración → General:** País **Colombia**, moneda **COP**, zona horaria **Bogotá**. **Idiomas:** Español.
6. Guarda. ✅

---

## 🛍️ ETAPA 2 — Conseguir productos en Dropi (1 hora)
1. Crea cuenta en **Dropi** (dropi.co) como vendedor.
2. Busca la categoría **belleza / cuidado de la piel**. Elige 3-5 productos (sérum, limpiador, protector solar...).
3. Verifica que tengan **registro INVIMA** (pregunta al proveedor).
4. En Shopify: **Apps → Shopify App Store →** busca **"Dropify - Import products from Dropi"** e instálala.
5. Conecta Dropify con tu cuenta Dropi.
6. **Importa** los productos: llegan con foto, precio y stock.
7. En **Productos**, mejora cada uno con `shopify-import/products.csv` y `fase-4-producto.md`, ponle **margen** (vende al doble o más del costo) y llena el **SEO** con `fase-5-seo.md`.

> 🔑 Cuando alguien compra, Dropify avisa a Dropi y **Dropi despacha + cobra el contraentrega**. Tú ganas la diferencia entre el costo Dropi y tu precio.

---

## 🎨 ETAPA 3 — Poner el diseño (tema Dawn) (1 hora)
1. **Tienda online → Temas →** ten **"Dawn"** (si no está: Agregar tema → biblioteca → Dawn).
2. 🛟 **Red de seguridad:** en el tema **··· → Duplicar** (copia por si acaso).
3. **Personalizar → Configuración → Colores/Tipografía:** usa `shopify-import/config/marca-colores-fuentes.md`. Sube tu **logo**.
4. **··· → Editar código** (solo vamos a pegar, tranquilo):
   - `templates/index.json` → borra y pega el de `shopify-import/templates/index.json`. **Guardar.**
   - `templates/product.json` → pega el de `shopify-import/templates/product.json`. **Guardar.**
   - `snippets/` → "Agregar snippet" `selva-trust-badges` → pega el `.liquid`. Repite con `selva-cart-upsell`.
   - En `sections/cart-drawer.liquid` y `main-cart-footer.liquid` pega `{% render 'selva-cart-upsell' %}` cerca del subtotal.

> Si algo se ve raro, vuelve al tema duplicado del paso 2. No se rompe nada permanente.

---

## 📄 ETAPA 4 — Crear páginas (FAQ, legales, quiz) (40 min)
1. **Tienda online → Páginas → Agregar página.**
2. Para cada una, pulsa **`<>` (Mostrar HTML)** y pega el bloque de `shopify-import/paginas-html/paginas.html`:
   FAQ · Privacidad · Términos · Devoluciones · Envíos · Contacto · Seguimiento.
3. Crea la página **"Descubre tu rutina"** y pega TODO `shopify-import/paginas-html/quiz-tipo-piel.html`.

> ⚖️ Haz revisar las páginas legales por un abogado cuando puedas.

---

## 🧭 ETAPA 5 — Menús (15 min)
**Tienda online → Navegación:**
- **Menú principal:** Inicio, Catálogo, Ofertas, Sérum, Kit, FAQ, Contacto, Seguir mi pedido.
- **Pie de página:** FAQ, Contacto, Seguimiento, Envíos, Devoluciones, Privacidad, Términos.

---

## 💳 ETAPA 6 — Pagos (45 min)
1. **Configuración → Pagos.**
2. **Mercado Pago:** conéctalo (tarjeta + PSE) siguiendo el asistente.
3. **Contraentrega:** "Métodos de pago manuales → Crear → Pago contra entrega (efectivo)". Actívalo.
   - Recomendado: app **Releasit COD Form** o **COD King** con **verificación por WhatsApp** (frena pedidos falsos).
4. Ofrece **5% por pago anticipado** para empujar el prepago.

---

## 🚚 ETAPA 7 — Envíos e impuestos (30 min)
1. **Configuración → Envíos:** tarifa Colombia (ej $12.000) + regla **Envío GRATIS desde $120.000**.
2. **Configuración → Impuestos:** IVA 19% donde aplique, precios con IVA incluido.

---

## ⭐ ETAPA 8 — Apps esenciales (30 min)
Desde **Apps → Shopify App Store** (todas con plan gratis/económico):
1. **Judge.me** (reseñas con foto). 2. **Klaviyo** (correos automáticos; textos en `marketing/flujo-carrito-abandonado-klaviyo.md`). 3. **AfterShip** (seguimiento). 4. **Releasit/COD King** (contraentrega).

---

## 🧪 ETAPA 9 — Probar antes de abrir (30 min)
1. Desde tu **celular**, entra como cliente.
2. Haz **compra de prueba** con **tarjeta** y otra con **contraentrega**.
3. Verifica el correo de confirmación y que la orden aparezca en Shopify y en Dropi.

---

## 🌐 ETAPA 10 — Dominio (20 min)
**Configuración → Dominios →** compra `selva.co` o conecta uno que tengas. Espera unas horas a que active.

---

## 🚀 ETAPA 11 — Primeras ventas (continuo)
Sigue `fase-7-entrega-final.md` (Primeras 100 ventas). En corto:
1. **Graba** los 5 anuncios con `marketing/plan-de-grabacion-anuncios.md`.
2. **Publica** en Instagram/TikTok 3-5 veces/semana.
3. **Avisa a tu círculo** por WhatsApp con oferta de lanzamiento + contraentrega.
4. Con reseñas listas, **pauta** 10-20 USD/día (guiones en `marketing/anuncios-meta-tiktok.md`).
5. Activa **carrito abandonado** en Klaviyo.

---

## 🗓️ Plan por días
| Día | Qué haces |
|---|---|
| **1** | Etapas 0-2 (cuenta + Dropi + productos) |
| **2** | Etapas 3-5 (diseño + páginas + menús) |
| **3** | Etapas 6-9 (pagos + envíos + apps + prueba) |
| **4+** | Dominio + grabar contenido + lanzar |

## ❓ Si te atascas
- Shopify tiene **chat de "Ayuda" 24/7**. Cada app también tiene soporte.
- Relee esta guía y `shopify-import/README-IMPORTAR.md`.

¡Tú puedes! Ve paso a paso, sin afán. 🌿
