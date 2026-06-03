# 🔁 Flujos de email/SMS/WhatsApp — Klaviyo · SELVÁ

> Copia y pega estos textos en Klaviyo. Incluye: carrito abandonado, checkout abandonado, bienvenida (-10%), post-compra y recompra. Tono cercano, colombiano neutro.

---

## ⚙️ Configuración previa
1. Conecta **Klaviyo** a Shopify (sincroniza eventos `Started Checkout`, `Added to Cart`, `Placed Order`).
2. Activa el **pop-up de bienvenida -10%** (Klaviyo Sign-up Form) con consentimiento.
3. Para **WhatsApp** usa un proveedor (WhatsApp API / app) — Klaviyo dispara, WhatsApp confirma. Pide opt-in.
4. Cumple Habeas Data (Ley 1581/2012): consentimiento + link para darse de baja.

---

## Flujo 1 — Carrito abandonado (Added to Cart, sin compra)
**Disparador:** "Added to Cart" / "Checkout Started" → filtro: no ha comprado.

**Email 1 · +1 hora — "¿Se te quedó algo? ✨"**
> Asunto: Tu piel te está esperando ✨
> Preview: Lo guardamos en tu carrito por ahora.
> Cuerpo: ¡Hola {{ first_name|default:"" }}! Vimos que dejaste tu rutina SELVÁ a medias. Te la guardamos para que la completes en 1 clic.
> [Botón] Retomar mi compra
> Recordatorio: 💵 Puedes pagar al recibir · 🚚 Envío 24-72h · ↩️ Garantía 30 días

**Email 2 · +24 horas — Prueba social**
> Asunto: +18.000 personas ya vieron resultados 🌿
> Cuerpo: No es solo un sérum: es una rutina que funciona. Mira lo que dicen quienes ya la usan. (incluir 2-3 reseñas ★)
> [Botón] Quiero mi piel luminosa

**Email 3 · +48 horas — Incentivo + urgencia honesta**
> Asunto: Un empujoncito para empezar hoy 💚
> Cuerpo: Para que arranques tu rutina, te dejamos envío gratis (o -5%) en este pedido. Aplica al finalizar. *El cupón vence en 24h.*
> [Botón] Completar con beneficio
> Código: EMPIEZAHOY

**WhatsApp (carritos de alto valor) · +3-6 horas**
> Hola {{ first_name }} 👋 soy de SELVÁ. Vi que te interesó nuestra rutina. ¿Te ayudo a completar el pedido? Puedes pagar al recibir 💵 y tienes 30 días de garantía. ¿Te confirmo el envío a tu ciudad?

---

## Flujo 2 — Checkout abandonado (Started Checkout con datos)
Mismo esquema que Flujo 1 pero más directo (ya dejó datos):
- **+30 min:** "Tu pedido está casi listo, solo falta confirmarlo." [Finalizar compra]
- **+12 h:** recordatorio + métodos de pago (incl. contraentrega).
- **+36 h:** incentivo suave.

---

## Flujo 3 — Bienvenida (-10%) (suscripción al pop-up)
**Email 1 · inmediato — Entregar el cupón**
> Asunto: Aquí está tu 10% 💚 (y tu guía gratis)
> Cuerpo: ¡Bienvenida/o a SELVÁ! Usa BIENVENIDA10 en tu primera compra. Te dejamos también la guía "Rutina de 3 pasos para piel colombiana".
> [Botón] Comprar con 10%

**Email 2 · +2 días — Educación + héroe**
> Asunto: La rutina de 3 pasos que tu piel necesita
> Cuerpo: Limpia, trata (Sérum Glow) y protege. Te explicamos por qué funciona.
> [Botón] Ver el Sérum Glow

**Email 3 · +4 días — Oferta del Kit + cierre**
> Asunto: Tu 10% está por vencer ⏳
> Cuerpo: Aprovecha el Kit Esencial con -29% + tu 10%. Paga al recibir.
> [Botón] Quiero el Kit

---

## Flujo 4 — Post-compra (Placed Order)
- **Inmediato:** confirmación + "cómo usar tu rutina" (reduce devoluciones).
- **+3 días:** tips de aplicación + invitación a WhatsApp para dudas.
- **+10 días:** pedir **reseña con foto** (incentivo: 10% próxima compra).
- **+21 días:** cross-sell del producto que falte en su rutina.

## Flujo 5 — Recompra / reposición
- **+45 días (Sérum 30 ml):** "Tu sérum está por acabarse, repón y ahorra." → ofrecer **suscripción -15%**.

---

## Métricas objetivo
| Flujo | Meta |
|---|---|
| Carrito abandonado | Recuperar 10-15% de carritos |
| Bienvenida | 25-40% open, 3-6% conversión |
| Post-compra reseñas | 8-12% dejan reseña |
| Recompra/suscripción | 15-25% de recompra a 60 días |
