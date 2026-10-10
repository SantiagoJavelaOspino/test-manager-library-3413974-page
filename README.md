# test-manager-library-3413974-page

> **Prueba técnica · Ficha ADSO 3413974**  
> Metodología: **Spec-Driven Development (SDD)**

Sitio público estático de presentación de *Manager Library*. No habla con la API (cumple ADR-001 y Spec oficial).

---

## 1. Características

- **Presentación del Proyecto:** Contexto de la ficha ADSO 3413974 y objetivos del reto.
- **Principios Constitucionales:** Resumen estructurado de los 12 principios de SDD (Artículos I al XII).
- **Arquitectura de Repositorios:** Mapeo de responsabilidades de los 6 repositorios independientes.
- **Guión Interactivo de Demostración:** Flujo guiado paso a paso para la sustentación ante el comité evaluador.
- **Independencia Total:** Construido como HTML5 semántico puro sin dependencias de backend ni llamadas a la API.

---

## 2. Ejecución Local

Simplemente abre `index.html` en cualquier navegador web, o sirve el directorio con cualquier servidor HTTP:

```bash
# Opción 1: Python HTTP Server
python -m http.server 8080

# Opción 2: Node.js Serve
npx serve -l 8080 .
```

Acceder a: `http://localhost:8080`

---

## 3. Despliegue con Docker

El repositorio incluye su propio `Dockerfile` basado en `nginx:alpine`:

```bash
docker build -t manager-library-page .
docker run -p 8080:80 manager-library-page
```

---

## 4. Stack Tecnológico de la Solución

| Capa | Tecnología Implementada | Justificación |
|---|---|---|
| **Frontend de Gestión** | React 18 + Vite 5 | SPA para bibliotecarios y administradores |
| **Backend API** | PHP 8.2 (Arquitectura Hexagonal) | Dominio puro sin dependencias (Art. I a III) |
| **Base de Datos** | PostgreSQL 16+ | Esquema `library`, transacciones y restricciones CHECK |
| **Sitio Público** | HTML5 Estático + Nginx | Presentación institucional independiente |
| **Infraestructura** | Docker Compose | Orquestación de servicios |
| **Herramientas** | Node.js (seed.js) | Sembrado de prueba vía API REST |

---

## 5. Los Seis Repositorios

| Repositorio | Responsabilidad |
|---|---|
| [`test-manager-library-3413974-docs`](https://github.com/SantiagoJavelaOspino/test-manager-library-3413974-docs) | Spec oficial, análisis SDD, ADRs y trazabilidad |
| [`test-manager-library-3413974-api`](https://github.com/SantiagoJavelaOspino/test-manager-library-3413974-api) | Backend API REST (PHP Hexagonal) |
| [`test-manager-library-3413974-app`](https://github.com/SantiagoJavelaOspino/test-manager-library-3413974-app) | Frontend React SPA |
| [`test-manager-library-3413974-page`](https://github.com/SantiagoJavelaOspino/test-manager-library-3413974-page) | Sitio público estático de presentación |
| [`test-manager-library-3413974-infra`](https://github.com/SantiagoJavelaOspino/test-manager-library-3413974-infra) | Contenedores y red con Docker Compose |
| [`test-manager-library-3413974-tool`](https://github.com/SantiagoJavelaOspino/test-manager-library-3413974-tool) | Sembrador automatizado de datos vía API |
