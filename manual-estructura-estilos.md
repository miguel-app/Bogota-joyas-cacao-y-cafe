# 📜 Manual de Estructura y Estilos (Design System & UX/UI)
## Plantilla de Landing Pages para Turismo y Viajes — Threads Travel

Este documento establece las especificaciones técnicas, reglas de UX/UI y el wireframe estructural para la creación de nuevas landing pages de paquetes de viaje de Threads Travel. Su objetivo es servir como único punto de verdad estilístico y estructural, de modo que cualquier desarrollador o LLM pueda generar una nueva página idéntica en diseño y experiencia con solo recibir la ficha técnica de un nuevo paquete.

---

## 🎨 1. Paleta de Colores (Design System)

La interfaz se rige por un esquema cromático premium y de alta legibilidad, diseñado para transmitir exclusividad y seguridad al usuario. Los siguientes tokens de colores CSS deben ser inyectados en la raíz `:root` del archivo de estilos:

```css
:root {
    /* Paleta Principal */
    --color-primary: #00234A;        /* Azul Marino (Confianza, Estructura, Fondos oscuros) */
    --color-accent: #CAA442;         /* Dorado Threads (Acción, Llamados a la Acción, Iconos, Destacados) */
    --color-accent-hover: #b89333;   /* Dorado Oscuro (Estado hover de botones) */
    
    /* Fondos y Superficies */
    --color-bg-light: #FFFFFF;       /* Blanco Puro (Contraste limpio, lecturas densas, checkout) */
    --color-bg-secondary: #F8F9FA;   /* Gris Bento (Fondos de secciones Bento y tarjetas secundarias) */
    --color-bg-muted: #ECEFF2;       /* Gris Tenue (Bordes y elementos deshabilitados o secundarios) */
    --color-border: #D1D8E0;         /* Gris Borde (Separadores suaves de acordeones y tarjetas) */
    
    /* Tipografía y Textos */
    --color-text-dark: #000305;      /* Negro Noche (Legibilidad máxima en fondo claro - WCAG AAA) */
    --color-text-muted: #4A5568;     /* Gris Carbón (Párrafos de descripción secundaria) */
    --color-text-light: #FFFFFF;     /* Blanco Texto (Textos sobre fondos oscuros / botones) */
}
```

---

## ✍️ 2. Tipografías y Estilos Jerárquicos

Se utiliza **Montserrat** de Google Fonts como única familia tipográfica para unificar la identidad visual de la marca y asegurar una lectura moderna.

### 🌐 Importación de Google Fonts
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400&display=swap" rel="stylesheet">
```

### 📏 Jerarquía de Tamaños y Pesos (CSS Standard)
*   **Fuente Global (`body`):** `'Montserrat', system-ui, -apple-system, sans-serif;`
*   **Encabezado Principal (`h1`):** `3.5rem` (56px) en escritorio / `1.85rem` (30px) en móvil. Peso: `400` o `600`.
*   **Subtítulos de Sección (`h2`):** `2.5rem` (40px) en escritorio / `2.0rem` (32px) en móvil. Peso: `600`.
*   **Títulos de Tarjetas/Acordeones (`h3`):** `1.4rem` (22.4px) en escritorio / `1.2rem` (19.2px) en móvil. Peso: `500` o `600`.
*   **Párrafos de Cuerpo (`p`):** `1.05rem` (16.8px). Peso: `300` (Light) para dar un aspecto premium, limpio y de fácil escaneo visual. `line-height: 1.6`.
*   **Texto Resaltado (`strong`):** Peso: `600` (Semibold).

---

## 🏗️ 3. Esquema y Estructura (Wireframe de Secciones)

El orden de las secciones en la página es estricto y responde a un embudo de conversión psicológica (AIDA: Atención, Interés, Deseo, Acción). A continuación se muestra la estructura HTML base con marcadores dinámicos `[INSERTAR_X]` que deben ser reemplazados en cada paquete nuevo.

### 🧱 Estructura HTML Base

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[INSERTAR_SEO_META_TITLE] | VIP Threads Travel</title>
    <meta name="description" content="[INSERTAR_SEO_META_DESCRIPTION]">
    <link rel="stylesheet" href="styles.css?v=1.1">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Estilos del Logotipo de Marca para evitar saltos de diseño (caching) */
        .logo-img {
            height: 56px;
            width: auto;
            display: block;
            transition: var(--transition-smooth);
        }
        .logo-img-footer {
            height: 42px;
            width: auto;
            display: block;
            margin-bottom: 12px;
            transition: var(--transition-smooth);
        }
        @media (max-width: 768px) {
            .logo-img {
                height: 38px;
            }
            .logo-img-footer {
                height: 32px;
            }
        }
        @media (max-width: 480px) {
            .logo-img {
                height: 32px;
            }
        }
    </style>
</head>
<body>

    <!-- 1. HEADER / NAVEGACIÓN -->
    <header class="header">
        <div class="container header-container">
            <a href="https://threadstravel.com/" class="logo-link" title="Inicio Threads Travel">
                <img src="https://threadstravel.com/wp-content/uploads/2026/05/cropped-Principal-fondo-oscuro-copia.png" alt="Threads Travel Logo" class="logo-img">
            </a>
            <nav class="nav">
                <a href="#experiencia" class="nav-link">La Experiencia</a>
                <a href="#itinerario" class="nav-link">Itinerario</a>
                <a href="#detalles" class="nav-link">Detalles</a>
                <a href="#faq" class="nav-link">Preguntas</a>
            </nav>
            <a href="[INSERTAR_ENLACE_WHATSAPP]" class="btn btn-outline" target="_blank">Contactar Concierge</a>
        </div>
    </header>

    <!-- 2. HERO SECTION -->
    <section class="hero">
        <div class="hero-bg-container">
            <img src="[INSERTAR_URL_IMAGEN_HERO]" alt="[INSERTAR_TEXTO_ALT_IMAGEN_HERO]" class="hero-bg-img" fetchpriority="high" decoding="async">
            <div class="hero-overlay"></div>
        </div>
        <div class="container hero-container">
            <h1 class="hero-title animate-fade-in">[INSERTAR_TITULAR_H1]<br><span class="highlight">[INSERTAR_FRASE_HIGHLIGHT_H1]</span></h1>
            <p class="hero-subtitle animate-fade-in-delayed">[INSERTAR_SUBTITULO_HERO]</p>
            <div class="hero-cta animate-fade-in-delayed-more">
                <a href="#detalles" class="btn btn-primary">ASEGURAR MI LUGAR VIP</a>
            </div>
        </div>
        <div class="hero-scroll-indicator">
            <span class="scroll-text">Deslizar para descubrir</span>
            <div class="scroll-arrow"><i class="fa-solid fa-chevron-down"></i></div>
        </div>
    </section>

    <!-- 3. BLOQUE DE EMPATÍA -->
    <section class="empathy-section" id="experiencia">
        <div class="container container-narrow">
            <div class="gold-divider"></div>
            <p class="empathy-text">
                [INSERTAR_TEXTO_EMPATIA]
            </p>
            <div class="gold-divider"></div>
        </div>
    </section>

    <!-- 4. PROPUESTA DE VALOR (Bento Grid) -->
    <section class="value-section" id="itinerario">
        <div class="container">
            <div class="section-header">
                <span class="section-tag">[INSERTAR_CATEGORIA_TAG]</span>
                <h2 class="section-title">[INSERTAR_TITULO_ITINERARIO]</h2>
                <p class="section-subtitle">[INSERTAR_SUBTITULO_ITINERARIO]</p>
            </div>

            <div class="bento-grid">
                <!-- Tarjeta Bento 1 (Grande - Ancho: 2 columnas en desktop) -->
                <div class="bento-card card-large">
                    <div class="card-icon"><i class="[INSERTAR_ICONO_FA_1]"></i></div>
                    <div class="card-content">
                        <h3>[INSERTAR_TITULO_VALOR_1]</h3>
                        <p class="card-intro">[INSERTAR_SUBTITULO_DESTACADO_1]</p>
                        <p>[INSERTAR_DESCRIPCION_VALOR_1]</p>
                    </div>
                </div>

                <!-- Tarjeta Bento 2 (Estándar - Ancho: 1 columna) -->
                <div class="bento-card">
                    <div class="card-icon"><i class="[INSERTAR_ICONO_FA_2]"></i></div>
                    <div class="card-content">
                        <h3>[INSERTAR_TITULO_VALOR_2]</h3>
                        <p class="card-intro">[INSERTAR_SUBTITULO_DESTACADO_2]</p>
                        <p>[INSERTAR_DESCRIPCION_VALOR_2]</p>
                    </div>
                </div>

                <!-- Tarjeta Bento 3 (Estándar - Ancho: 1 columna) -->
                <div class="bento-card">
                    <div class="card-icon"><i class="[INSERTAR_ICONO_FA_3]"></i></div>
                    <div class="card-content">
                        <h3>[INSERTAR_TITULO_VALOR_3]</h3>
                        <p class="card-intro">[INSERTAR_SUBTITULO_DESTACADO_3]</p>
                        <p>[INSERTAR_DESCRIPCION_VALOR_3]</p>
                    </div>
                </div>

                <!-- Tarjeta Bento 4 (Grande con Imagen de Fondo - Ancho: 2 columnas en desktop) -->
                <div class="bento-card card-large card-has-img">
                    <div class="card-img-container">
                        <img src="[INSERTAR_URL_IMAGEN_VALOR_4]" alt="[INSERTAR_ALT_IMAGEN_VALOR_4]" class="card-img" loading="lazy" decoding="async">
                        <div class="card-img-overlay"></div>
                    </div>
                    <div class="card-content-overlay">
                        <div class="card-icon-light"><i class="[INSERTAR_ICONO_FA_4]"></i></div>
                        <h3>[INSERTAR_TITULO_VALOR_4]</h3>
                        <p class="card-intro">[INSERTAR_SUBTITULO_DESTACADO_4]</p>
                        <p>[INSERTAR_DESCRIPCION_VALOR_4]</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 5. DETALLES, PRECIO Y FORMULARIO (Checkout de Dos Columnas) -->
    <section class="details-section" id="detalles">
        <div class="container">
            <div class="details-grid">
                
                <!-- Columna Izquierda: Especificaciones e Inclusiones -->
                <div class="details-info">
                    <span class="section-tag-light">Especificaciones</span>
                    <h2 class="details-title">Los Detalles de su Travesía</h2>
                    
                    <div class="specs-grid">
                        <div class="spec-item">
                            <span class="spec-label">Duración</span>
                            <span class="spec-value">[INSERTAR_DURACION]</span>
                        </div>
                        <div class="spec-item">
                            <span class="spec-label">Tipo de Experiencia</span>
                            <span class="spec-value">[INSERTAR_TIPO_EXPERIENCIA]</span>
                        </div>
                        <div class="spec-item">
                            <span class="spec-label">Idiomas</span>
                            <span class="spec-value">[INSERTAR_IDIOMAS]</span>
                        </div>
                        <div class="spec-item">
                            <span class="spec-label">Dificultad</span>
                            <span class="spec-value">[INSERTAR_DIFICULTAD]</span>
                        </div>
                    </div>

                    <div class="inclusions-container">
                        <h3>Qué incluye esta experiencia</h3>
                        <ul class="inclusions-list">
                            <!-- Repetir según los items incluidos del tour -->
                            <li><span class="list-bullet-check">✓</span> [INSERTAR_INCLUSION_1]</li>
                            <li><span class="list-bullet-check">✓</span> [INSERTAR_INCLUSION_2]</li>
                            <li><span class="list-bullet-check">✓</span> [INSERTAR_INCLUSION_N]</li>
                        </ul>

                        <h3 class="exclusions-title">No incluye</h3>
                        <ul class="exclusions-list">
                            <!-- Repetir según los items excluidos del tour -->
                            <li><span class="list-bullet-cross">✗</span> [INSERTAR_EXCLUSION_1]</li>
                            <li><span class="list-bullet-cross">✗</span> [INSERTAR_EXCLUSION_N]</li>
                        </ul>
                    </div>
                </div>

                <!-- Columna Derecha: Tarjeta de Reserva y Conversión -->
                <div class="booking-column">
                    <div class="booking-card">
                        <div class="booking-urgency">
                            <i class="fa-solid fa-circle-exclamation"></i> CUPOS ESTRICTAMENTE LIMITADOS
                        </div>
                        
                        <div class="booking-header">
                            <span class="price-label">Inversión por persona</span>
                            <span class="price-value">$[INSERTAR_PRECIO_NUMERICO] <span class="currency">USD</span></span>
                        </div>
                        
                        <div class="booking-body">
                            <p class="booking-warning-text">
                                [INSERTAR_TEXTO_ADVERTENCIA_CUPO_LIMITADO]
                            </p>
                            
                            <!-- Formulario de Reserva Integrado -->
                            <form id="booking-form" class="booking-form" action="[INSERTAR_ACTION_FORMULARIO_O_HANDLER]" method="POST">
                                <div class="form-group">
                                    <label for="booking-name" class="form-label">Nombre Completo</label>
                                    <input type="text" id="booking-name" name="name" class="form-control" placeholder="Ej. Juan Pérez" required>
                                </div>
                                <div class="form-group">
                                    <label for="booking-date" class="form-label">Fecha Estimada del Tour</label>
                                    <input type="date" id="booking-date" name="tour_date" class="form-control" required>
                                </div>
                                <div class="form-group">
                                    <label for="booking-phone" class="form-label">Teléfono Móvil (WhatsApp)</label>
                                    <input type="tel" id="booking-phone" name="phone" class="form-control" placeholder="Ej. +57 300 123 4567" required>
                                </div>
                                <div class="form-group">
                                    <label for="booking-email" class="form-label">Correo Electrónico</label>
                                    <input type="email" id="booking-email" name="email" class="form-control" placeholder="Ej. juan@correo.com" required>
                                </div>
                                
                                <button type="submit" class="btn btn-primary btn-block btn-pulse">
                                    <i class="fa-brands fa-whatsapp"></i> DISEÑAR MI RUTA VIP
                                </button>
                            </form>
                            
                            <p class="booking-footer-note">
                                Al enviar sus datos, nuestro equipo de Concierges de Viajes se comunicará directamente con usted en menos de 15 minutos para validar disponibilidad y ajustar el menú a sus necesidades o restricciones alimenticias.
                            </p>
                        </div>
                    </div>
                    
                    <!-- Sección de Confianza / Trust Section Adyacente -->
                    <div class="trust-container">
                        <div class="trust-item">
                            <div class="trust-icon"><i class="fa-solid fa-passport"></i></div>
                            <div class="trust-content">
                                <strong>Registro Nacional de Turismo</strong>
                                <span>RNT Licencia No. [INSERTAR_NUMERO_RNT]</span>
                            </div>
                        </div>
                        <div class="trust-item">
                            <div class="trust-icon text-stars"><i class="fa-solid fa-star"></i> 5.0</div>
                            <div class="trust-content">
                                <strong>Opiniones en Google</strong>
                                <span>Reseñas de 5 estrellas basadas en viajeros VIP</span>
                            </div>
                        </div>
                    </div>
                </div>
                
            </div>
        </div>
    </section>

    <!-- 6. SECCIÓN DE PREGUNTAS FRECUENTES (FAQ Acordeón) -->
    <section class="faq-section" id="faq">
        <div class="container container-medium">
            <div class="section-header">
                <span class="section-tag">Resolviendo dudas</span>
                <h2 class="section-title">Preguntas Frecuentes</h2>
                <p class="section-subtitle">Respuestas a sus inquietudes para que planifique su travesía con absoluta tranquilidad.</p>
            </div>

            <div class="accordion">
                <!-- FAQ Item 1 -->
                <div class="accordion-item">
                    <button class="accordion-header" aria-expanded="false">
                        <h3>[INSERTAR_PREGUNTA_1]</h3>
                        <span class="accordion-icon"><i class="fa-solid fa-plus"></i></span>
                    </button>
                    <div class="accordion-collapse">
                        <div class="accordion-body">
                            <p>[INSERTAR_RESPUESTA_1]</p>
                        </div>
                    </div>
                </div>

                <!-- FAQ Item 2 -->
                <div class="accordion-item">
                    <button class="accordion-header" aria-expanded="false">
                        <h3>[INSERTAR_PREGUNTA_2]</h3>
                        <span class="accordion-icon"><i class="fa-solid fa-plus"></i></span>
                    </button>
                    <div class="accordion-collapse">
                        <div class="accordion-body">
                            <p>[INSERTAR_RESPUESTA_2]</p>
                        </div>
                    </div>
                </div>

                <!-- FAQ Item 3 -->
                <div class="accordion-item">
                    <button class="accordion-header" aria-expanded="false">
                        <h3>[INSERTAR_PREGUNTA_3]</h3>
                        <span class="accordion-icon"><i class="fa-solid fa-plus"></i></span>
                    </button>
                    <div class="accordion-collapse">
                        <div class="accordion-body">
                            <p>[INSERTAR_RESPUESTA_3]</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 7. FOOTER -->
    <footer class="footer">
        <div class="container footer-container">
            <div class="footer-brand">
                <a href="https://threadstravel.com/" class="logo-link" title="Inicio Threads Travel">
                    <img src="https://threadstravel.com/wp-content/uploads/2026/05/cropped-Principal-fondo-oscuro-copia.png" alt="Threads Travel Logo" class="logo-img-footer">
                </a>
                <p>Tejiendo experiencias memorables, libres de estrés.</p>
            </div>
            <div class="footer-copy">
                &copy; 2026 Threads Travel. Todos los derechos reservados. | RNT No. [INSERTAR_NUMERO_RNT]
            </div>
        </div>
    </footer>

    <!-- Interactive JS for Accordion -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const accordionHeaders = document.querySelectorAll('.accordion-header');
            
            accordionHeaders.forEach(header => {
                header.addEventListener('click', () => {
                    const isExpanded = header.getAttribute('aria-expanded') === 'true';
                    const activeCollapse = header.nextElementSibling;
                    const icon = header.querySelector('.accordion-icon i');

                    // Close all other items
                    accordionHeaders.forEach(otherHeader => {
                        if (otherHeader !== header) {
                            otherHeader.setAttribute('aria-expanded', 'false');
                            otherHeader.nextElementSibling.style.maxHeight = null;
                            otherHeader.querySelector('.accordion-icon i').className = 'fa-solid fa-plus';
                        }
                    });

                    if (isExpanded) {
                        header.setAttribute('aria-expanded', 'false');
                        activeCollapse.style.maxHeight = null;
                        icon.className = 'fa-solid fa-plus';
                    } else {
                        header.setAttribute('aria-expanded', 'true');
                        activeCollapse.style.maxHeight = activeCollapse.scrollHeight + 'px';
                        icon.className = 'fa-solid fa-minus';
                    }
                });
            });
        });
    </script>
</body>
</html>
```

---

## 🛠️ 4. Componentes Clave y Reglas de UX/UI

Para asegurar la máxima tasa de conversión (CRO) y mantener el aspecto visual unificado, se deben respetar de forma estricta las siguientes reglas CSS para los componentes principales:

### 👆 4.1 Comportamiento y Estilos de los Botones (CTA)

Los botones principales deben destacar sobre la interfaz usando el color dorado e invitar a la acción mediante micro-interacciones suaves.

```css
/* Botón Base */
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 16px 36px;
    border-radius: 8px;
    font-family: var(--font-body);
    font-weight: 500;
    font-size: 0.95rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    text-decoration: none;
    cursor: pointer;
    transition: var(--transition-smooth);
    border: none;
}

/* Botón Dorado (CTA Primario) */
.btn-primary {
    background-color: var(--color-accent);
    color: #FFFFFF;
    box-shadow: 0 4px 15px rgba(202, 164, 66, 0.35);
}

.btn-primary:hover {
    background-color: var(--color-accent-hover);
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(202, 164, 66, 0.45);
}

/* Botón Delineado (Outline / Secundario) */
.btn-outline {
    background-color: transparent;
    border: 1px solid var(--color-accent);
    color: var(--color-accent);
}

.btn-outline:hover {
    background-color: var(--color-accent);
    color: #FFFFFF;
    transform: translateY(-2px);
}

.btn-block {
    width: 100%;
    display: flex;
}

/* Micro-animación de Pulso Continuo (Llamado de atención constante) */
.btn-pulse {
    animation: subtle-pulse 2s infinite;
}

@keyframes subtle-pulse {
    0% {
        box-shadow: 0 4px 15px rgba(202, 164, 66, 0.35);
    }
    50% {
        box-shadow: 0 4px 25px rgba(202, 164, 66, 0.6);
    }
    100% {
        box-shadow: 0 4px 15px rgba(202, 164, 66, 0.35);
    }
}
```

### 📋 4.2 Formulario de Reserva y Sección de Confianza (Trust Section)

El formulario debe mitigar la fricción de entrada solicitando únicamente información esencial para que el equipo comercial agilice el cierre por WhatsApp/Llamada.

```css
/* Contenedor del Formulario */
.booking-form {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.form-group {
    display: flex;
    flex-direction: column;
    gap: 8px;
    align-items: stretch;
}

.form-label {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 600;
    color: var(--color-primary);
    transition: var(--transition-smooth);
}

.form-control {
    width: 100%;
    padding: 14px 16px;
    border: 1px solid var(--color-border);
    border-radius: 8px;
    font-family: var(--font-body);
    font-size: 0.95rem;
    font-weight: 400;
    color: var(--color-text-dark);
    background-color: #FFFFFF;
    transition: var(--transition-smooth);
    box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.02);
}

.form-control::placeholder {
    color: rgba(0, 35, 74, 0.4);
}

.form-control:focus {
    outline: none;
    border-color: var(--color-accent);
    background-color: #FFFFFF;
    box-shadow: 0 0 0 4px rgba(202, 164, 66, 0.15);
}

/* Resaltado del label al enfocar el input */
.form-group:focus-within .form-label {
    color: var(--color-accent);
}

/* Estilo para los campos de tipo date */
input[type="date"].form-control {
    font-family: var(--font-body);
    color: var(--color-text-dark);
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none' stroke='%23CAA442' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Crect x='3' y='4' width='18' height='18' rx='2' ry='2'%3E%3C/rect%3E%3Cline x1='16' y1='2' x2='16' y2='6'%3E%3C/line%3E%3Cline x1='8' y1='2' x2='8' y2='6'%3E%3C/line%3E%3Cline x1='3' y1='10' x2='21' y2='10'%3E%3C/line%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 16px center;
    background-size: 18px 18px;
    padding-right: 48px;
}

input[type="date"].form-control::-webkit-calendar-picker-indicator {
    color: var(--color-accent);
    opacity: 0.8;
    cursor: pointer;
    transition: var(--transition-smooth);
}

input[type="date"].form-control::-webkit-calendar-picker-indicator:hover {
    opacity: 1;
}


/* Sección de Confianza (Trust Container) - Ubicada justo debajo de la booking-card */
.trust-container {
    margin-top: 24px;
    display: flex;
    flex-direction: column;
    gap: 16px;
    background-color: var(--color-bg-secondary);
    padding: 20px;
    border-radius: 12px;
    border: 1px solid var(--color-border);
}

.trust-item {
    display: flex;
    align-items: center;
    gap: 16px;
}

.trust-icon {
    width: 40px;
    height: 40px;
    background-color: rgba(0, 35, 74, 0.05);
    color: var(--color-primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
}

.trust-icon.text-stars {
    color: var(--color-accent);
    font-weight: 700;
    font-size: 0.85rem;
}

.trust-content {
    display: flex;
    flex-direction: column;
}

.trust-content strong {
    font-size: 0.85rem;
    color: var(--color-text-dark);
}

.trust-content span {
    font-size: 0.75rem;
    color: var(--color-text-muted);
}
```

---

## 🤖 5. Instrucciones para Futuros LLMs (System Prompt / Prompt Inyectable)

> [!IMPORTANT]
> **INSTRUCCIÓN OBLIGATORIA DE DISEÑO Y ESTRUCTURA:**
> Actúa como un desarrollador frontend senior especializado en CRO. Al recibir los datos de un nuevo paquete turístico o viaje, debes generar el archivo `index.html` basándote estrictamente en el esquema de este manual. No debes modificar bajo ninguna circunstancia la paleta de colores (`--color-primary`, `--color-accent`, etc.), los tamaños de fuente, los márgenes (`container`), el Bento Grid de la sección de itinerario o la estructura flotante de dos columnas de la sección de detalles.
> Tu única tarea es mapear los nuevos textos descriptivos del viaje, actualizar los marcadores de posición dinámicos `[INSERTAR_...]` en el código HTML, y asegurar que todas las imágenes y enlaces reflejen el destino solicitado, respetando al 100% las clases del framework visual vanilla CSS definido en este documento.
