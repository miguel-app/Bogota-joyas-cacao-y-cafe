# 📜 Manifesto & Standard: Modern Fullstack Engineering 2026

## 🎯 Visión General
Este documento define el estándar técnico para el stack **React (Vite) + Supabase + Vercel**. El objetivo es construir productos que no solo funcionen, sino que proyecten autoridad técnica, seguridad inquebrantable y una conversión optimizada.

---

## 🏗️ 1. Backend & Data Architecture (Supabase Focus)

### 🔐 Seguridad y Acceso (RLS)
- **Principio de Mínimo Privilegio:** Ninguna tabla tiene acceso público. Todo se rige por políticas de Row Level Security (RLS).
- **JWT Awareness:** Las políticas deben validar no solo el `auth.uid()`, sino también metadatos del JWT (ej. `email_confirmed`).
- **No Service Key en Client-Side:** El uso de `service_role` queda restringido estrictamente a Edge Functions para procesos administrativos.

### 🔌 Integridad de Datos
- **Type-Safety:** Generación obligatoria de tipos de TypeScript mediante Supabase CLI. Sincronización en cada migración.
- **Validación con Zod:** Los esquemas de Zod deben ser el único punto de verdad para la validación de formularios en el frontend y la limpieza de datos antes de entrar a la DB.

---

## 🛡️ 2. Security Protocol (Vercel & Infrastructure)

### 🚀 Despliegue Seguro
- **Environment Isolation:** Variables de entorno diferenciadas estrictamente entre `development`, `preview` y `production`.
- **Content Security Policy (CSP):** Configuración de headers en `vercel.json` para mitigar ataques XSS y Clickjacking.
- **Secret Management:** Uso de Vercel Secrets para llaves de API de terceros (Stripe, OpenAI, Resend).

### 🔍 Observabilidad
- **Structured Logging:** Implementación de logs limpios. Prohibido subir `console.log` a producción.
- **Auditoría:** Registro de cambios críticos en tablas sensibles mediante triggers de PostgreSQL.

---

## ⚡ 3. High-Conversion Landing Philosophy

### 🧠 Psicología de Identidad
- **Fricción Cero:** El LCP (Largest Contentful Paint) debe ser < 1.2s. La velocidad es el primer factor de confianza.
- **Diseño Bento / Modular:** Estructura de información en contenedores claros que faciliten el escaneo visual rápido.
- **Micro-copy de Acción:** Reemplazo de etiquetas genéricas por verbos de resultado en primera persona (ej: "Optimizar mi flujo" vs "Enviar").

### 🛠️ Reglas de Frontend (Vite)
- **Componentes Atómicos:** Uso de Radix UI / Shadcn UI para garantizar accesibilidad (WCAG 2.1) y consistencia.
- **Optimización de Assets:** Imágenes en formato WebP/AVIF, fuentes auto-hospedadas para evitar Layout Shifts (CLS).
- **Client-Side Skeletons:** Uso de esqueletos de carga en lugar de spinners para mejorar la percepción de velocidad.

---

## 📝 4. Checklist de Definición de "Hecho" (DoD)

- [ ] **DB:** ¿La tabla tiene RLS activo y probado?
- [ ] **Tipado:** ¿Se han regenerado los tipos de Supabase?
- [ ] **Validación:** ¿Zod está interceptando los inputs del usuario?
- [ ] **Performance:** ¿Puntaje de Lighthouse en Performance > 90?
- [ ] **Seguridad:** ¿Están las API Keys sensibles ocultas y rotadas?
- [ ] **Identidad:** ¿El CTA principal es visible sin hacer scroll (Above the fold)?

---

## 🛠️ Stack Tecnológico Referencia
- **Frontend:** React 19+, Vite, Tailwind CSS.
- **Estado/Data:** TanStack Query (para caching) o Supabase Hooks.
- **Seguridad:** Zod, Auth Helpers de Supabase.
- **Infra:** Vercel Edge Network.