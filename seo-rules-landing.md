# 🚀 Manual de Reglas SEO para Landing Pages — Threads Travel

Este documento establece las directrices obligatorias de optimización para motores de búsqueda (SEO) que deben aplicarse a cada nueva página de producto/paquete para garantizar su indexación y posicionamiento orgánico rápido.

---

## 1. Arquitectura de URL (Slugs Limpios)
La URL debe ser corta, fácil de leer para el usuario y contener la palabra clave principal de venta. Evita números aleatorios o caracteres especiales.

* **Fórmula:** `threadstravel.com/paquetes/[destino-o-evento]-[año]`
* **Ejemplo Correcto:** `threadstravel.com/paquetes/ricardo-arjona-bogota-2026`
* **Incorrecto:** `threadstravel.com/paquete-vip-oferta-final-arjona-12354`

---

## 2. Etiquetas de Títulos Meta y Snippets (Optimización SERP)
Es lo primero que el usuario ve en Google. Debe generar el clic (CTR elevado) combinando la palabra clave con el beneficio de exclusividad.

### 🔵 Meta Title (Máximo 60 caracteres)
Debe incluir la palabra clave al principio y el nombre de la marca al final.
* **Fórmula:** Paquete [Nombre del Evento/Destino] [Año] | VIP Threads Travel
* **Ejemplo:** `Paquete Ricardo Arjona Bogotá 2026 | VIP Threads Travel`

### 🟢 Meta Description (Máximo 155 caracteres)
Debe ser un resumen persuasivo que incluya el precio inicial o un gancho de urgencia, terminando con un llamado a la acción.
* **Ejemplo:** `Asegura tu entrada en Platea para Ricardo Arjona en Bogotá el 26 de julio. Paquete VIP con hotel y traslados incluidos. ¡Cupos limitados, reserva hoy!`

---

## 3. Jerarquía de Encabezados (Estructura H1, H2, H3)
Los robots de Google leen el sitio de arriba a abajo. Solo puede existir **un solo H1 por página**, el cual debe contener la palabra clave principal.

* **`<h1>` (Título Principal):** Debe incluir la intención de búsqueda de compra. 
  * *Ejemplo:* `Paquetes VIP para el Concierto de Ricardo Arjona en Bogotá`
* **`<h2>` (Subtítulos de Sección):** Se usan para desglosar los beneficios y la logística.
  * *Ejemplo 1:* `¿Qué incluye el Paquete Todo Incluido a Bogotá?`
  * *Ejemplo 2:* `Cronograma e Itinerario del Viaje`
* **`<h3>` (Secciones Menores):** Ideal para desglosar subelementos o las preguntas frecuentes.
  * *Ejemplo:* `¿Cómo reservar mi entrada a Platea?`

---

## 4. Optimización de Contenido y Palabras Clave (SEO On-Page)
* **Keyword Density (Densidad):** La palabra clave principal (ej. *Paquete Ricardo Arjona Bogotá*) debe aparecer de forma natural en el primer párrafo, a mitad del texto y cerca del cierre. No abuses (evita el *keyword stuffing*).
* **Palabras clave secundarias (LSI):** Enriquece el texto con términos semánticos relacionados que la gente busca: *"entradas Platea Bogotá"*, *"hoteles cerca del concierto"*, *"transporte seguro Bogotá"*, *"turismo de conciertos"*.
* **Enlaces Internos:** Añade al menos un enlace hacia la página de inicio de Threads Travel o a otros paquetes relacionados del mismo destino.

---

## 5. SEO Técnico y Experiencia de Usuario (Core Web Vitals)
Las landing pages de conversión viven del tráfico móvil (Instagram, WhatsApp). Google penaliza los sitios lentos.

* **Optimización del Logotipo y Multimedia:** * El logo de Threads Travel y cualquier imagen del destino **deben estar en formato `.webp`** (nunca `.png` o `.jpg` pesados en la web). Ninguna imagen debe pesar más de 100 KB.
  * Agrega siempre la etiqueta `ALT` (Texto alternativo) a las imágenes. *Ejemplo:* `<img src="logo.webp" alt="Logotipo oficial de Threads Travel en color azul y dorado">`.
* **Velocidad de Carga:** La página debe cargar en menos de 2.5 segundos. Evita scripts innecesarios o animaciones pesadas en el primer pantallazo (Hero section).

---

## 6. Datos Estructurados (Schema Markup)
Para que Google entienda que vendes un producto o un evento y muestre "fragmentos enriquecidos" (como el precio o las estrellas en los resultados de búsqueda), se debe inyectar código Schema de tipo **Product** o **Event**.

* **Campos obligatorios a configurar en el plugin de SEO (como RankMath o Yoast):**
  * `Name`: Paquete VIP Ricardo Arjona Bogotá
  * `Price`: 520
  * `PriceCurrency`: USD
  * `Availability`: InStock