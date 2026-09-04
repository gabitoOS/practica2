# practica2   Diagrama de Flujo y Modelado de Amenazas (STRIDE)

Este repositorio contiene la entrega de la Práctica 2, correspondiente al análisis de seguridad y flujo de procesos para el **Escenario 1 (Autenticación y Control de Acceso)**.

---

## 1. Diagrama de Flujo (Escenario 1)

El siguiente diagrama en **Mermaid** representa el flujo de datos y validación de una petición de inicio de sesión segura:

```mermaid
graph TD
    A[Usuario / Cliente] -->|1. Solicita acceso (HTTPS)| B[WAF / Firewall de Red]
    B -->|2. Tráfico filtrado| C[Servidor de Aplicación]
    C -->|3. Consulta de credenciales| D[(Base de Datos MySQL)]
    D -->|4. Valida/Rechaza usuario| C
    C -->|5. Retorna Token de Sesión (JWT)| A
