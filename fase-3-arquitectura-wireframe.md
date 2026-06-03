# FASE 3 — Arquitectura y replicación inteligente

> **Replicamos** arquitectura, flujo visual, orden de bloques, estrategia de venta, técnicas de persuasión y optimización móvil.
> **NO copiamos** textos, imágenes, logos, marcas ni contenido protegido. Todo el copy de SELVÁ es original.

---

## 3.1 Principios de diseño (UX/UI)
- **Móvil primero**: >70% del tráfico colombiano es móvil. Cada bloque se diseña primero en 390px.
- **Jerarquía estricta**: un mensaje dominante por sección, un CTA principal por pantalla.
- **Regla de los 5 segundos**: el visitante debe entender qué se vende y por qué le conviene sin hacer scroll.
- **Velocidad**: imágenes WebP, lazy-load, hero < 200 KB, fuentes del sistema/2 familias máx.
- **Accesibilidad y confianza**: contraste AA, badges visibles, microcopy honesto.

## 3.2 Flujo visual (escaneo en Z / F)
1. Logo + propuesta → 2. Hero con CTA → 3. Prueba social inmediata → 4. Beneficios →
5. Problema/Solución → 6. Producto héroe + bundle → 7. Testimonios/antes-después →
8. Garantía/Trust → 9. FAQ → 10. CTA de cierre + captura email.

---

## 3.3 Wireframe de la HOME (mobile-first, de arriba a abajo)

```
┌───────────────────────────────────────────┐
│ ⛰ ANUNCIO BARRA SUPERIOR (announcement)     │  ← Envío gratis > $120.000 · Contraentrega
├───────────────────────────────────────────┤
│ ☰   SELVÁ   🔍 👤 🛒(2)                       │  ← Header sticky
├───────────────────────────────────────────┤
│                                             │
│        [ HERO full-bleed ]                  │
│  H1: Piel luminosa en 4 semanas             │
│  Sub: Sérum Glow · Vit C 10% + Niacinamida  │
│  [ COMPRAR AHORA ]  [ Hacer el quiz ]       │
│  ★4,8 · 2.300+ reseñas                       │
├───────────────────────────────────────────┤
│  🚚 Envío 24-72h · 🔒 Pago seguro ·          │  ← Barra de confianza (trust bar)
│  ↩ 30 días garantía · 🧪 Registro INVIMA     │
├───────────────────────────────────────────┤
│  BENEFICIOS (4 íconos)                       │
│  ✦ Luminosidad ✦ Menos manchas               │
│  ✦ Hidratación ✦ Apto piel sensible          │
├───────────────────────────────────────────┤
│  PROBLEMA / SOLUCIÓN                          │
│  "¿Piel apagada, manchas, resequedad?"       │
│  → Rutina de 3 pasos (Limpia·Trata·Protege)  │
├───────────────────────────────────────────┤
│  PRODUCTO HÉROE (card grande)                │
│  [img] Sérum Glow  ★4,8  $89.000             │
│  [ Agregar al carrito ]                       │
├───────────────────────────────────────────┤
│  OFERTA ANCLA — KIT ESENCIAL 3 PASOS         │
│  Antes $267.000  Ahora $189.000 (-29%)       │
│  [ Quiero el kit ]   ⏳ Quedan X unidades     │
├───────────────────────────────────────────┤
│  PRUEBA SOCIAL (carrusel reseñas + UGC)      │
│  ★★★★★ "María, Bogotá" + foto antes/después  │
├───────────────────────────────────────────┤
│  TESTIMONIOS / RESULTADOS (antes-después)    │
├───────────────────────────────────────────┤
│  GARANTÍA SIN RIESGO (banda destacada)       │
│  "30 días o te devolvemos tu dinero"         │
├───────────────────────────────────────────┤
│  FAQ (acordeón 6-8 preguntas)                │
├───────────────────────────────────────────┤
│  CAPTURA EMAIL / QUIZ (-10%)                 │
├───────────────────────────────────────────┤
│  FOOTER: menú, legales, pagos, redes, WA     │
└───────────────────────────────────────────┘
```

## 3.4 Wireframe de la PÁGINA DE PRODUCTO (PDP)

```
┌───────────────────────────────────────────┐
│ Breadcrumb: Inicio / Sérums / Sérum Glow    │
├──────────────────────┬──────────────────────┤
│ [Galería de imágenes]│ H1 Sérum Glow         │
│  (swipe en móvil)    │ ★4,8 · 2.300 reseñas  │
│  + video corto       │ Precio $89.000        │
│                      │ ✓ beneficio 1         │
│                      │ ✓ beneficio 2         │
│                      │ ✓ beneficio 3         │
│                      │ [Tamaño/variante]     │
│                      │ ◉ Compra única        │
│                      │ ◉ Suscripción -15%    │
│                      │ [ AGREGAR — $89.000 ] │
│                      │ 🚚 ↩ 🔒 (trust sobre  │
│                      │     y bajo el CTA)    │
│                      │ ⏳ Stock / urgencia    │
├──────────────────────┴──────────────────────┤
│ UPSELL: "Complétalo con el Kit y ahorra 29%" │
├───────────────────────────────────────────┤
│ DESCRIPCIÓN DE VENTAS (beneficio→cómo→prueba)│
├───────────────────────────────────────────┤
│ CARACTERÍSTICAS / INGREDIENTES CLAVE          │
├───────────────────────────────────────────┤
│ CÓMO USAR (3 pasos + gif)                     │
├───────────────────────────────────────────┤
│ TABLA COMPARATIVA (SELVÁ vs. genérico)        │
├───────────────────────────────────────────┤
│ RESEÑAS (estrellas, fotos, filtros)           │
├───────────────────────────────────────────┤
│ GARANTÍA + FAQ del producto                   │
├───────────────────────────────────────────┤
│ CROSS-SELL: "Otros lo combinan con…"          │
├───────────────────────────────────────────┤
│ STICKY ADD-TO-CART (móvil, siempre visible)   │
└───────────────────────────────────────────┘
```

## 3.5 Flujo del CARRITO y CHECKOUT
```
Carrito (drawer lateral)
 ├─ Línea de producto + foto + cantidad
 ├─ Barra de progreso "Te faltan $X para envío gratis"
 ├─ Upsell 1-clic: "Agrega Hidratante con FPS (-20%)"
 ├─ Trust badges (pago seguro, contraentrega, 30 días)
 ├─ Cupones / notas
 └─ [ Finalizar compra ]  →  Checkout Shopify
                              ├─ Datos envío (ciudad/depto Colombia)
                              ├─ Métodos: Tarjeta · PSE · Nequi · Contraentrega
                              └─ Confirmación + seguimiento (WhatsApp/email)
```

## 3.6 Optimización móvil (checklist)
- Header sticky con carrito siempre visible.
- Sticky "Agregar al carrito" en PDP.
- Botones ≥ 44px, fuentes ≥ 16px, tap targets espaciados.
- Galería con swipe; acordeones para texto largo.
- Carga diferida de reseñas y video.
- Checkout con teclado numérico para teléfono/documento.

## 3.7 Qué replicamos vs. qué creamos (tabla de cumplimiento legal)
| ✅ Sí replicamos (patrón/estrategia) | 🚫 No copiamos (propiedad de terceros) |
|---|---|
| Orden de bloques de la home/PDP | Textos de competidores |
| Flujo quiz → PDP → bundle → upsell | Imágenes/fotos de producto ajenas |
| Ubicación de trust badges | Logos y nombres de marca |
| Estrategia de bundle y suscripción | Reseñas/testimonios reales de terceros |
| Técnicas de escasez/urgencia honesta | Contenido protegido por copyright |
| Estructura de FAQ y garantía | Tipografías/licencias pagas sin permiso |
