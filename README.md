# base-tecnica

Base técnica común del curso (Grupo 6). Es el paquete sobre el que se apoyan los demás grupos:

- **Identidad y login:** emite el JWT de sesión y publica el JWKS con el que todos los servicios lo validan.
- **Estructura del frontend:** app shell donde se componen los microcomponentes de cada paquete.
- **Contratos OpenAPI:** reúne los contratos de los 8 paquetes y lleva el registro de servicios.
- **Integración entre paquetes:** Compose de integración, e2e entre servicios y ensamblaje LPS.

Los lineamientos técnicos (stack, estructura, contenedores, seguridad y pruebas) están en el documento
**DAS — Desarrollo de Microservicios** del curso.

> **Estado:** esqueleto del Hito 0 importado desde el repo de Jordán
> ([Jordanariash/ejecu-microservicio-BT-grupo6](https://github.com/Jordanariash/ejecu-microservicio-BT-grupo6)),
> con la estructura publicada en el classroom. Todavía falta código para que el pipeline pase
> ([#1](https://github.com/tinioviedo/base-tecnica/issues/1), [#5](https://github.com/tinioviedo/base-tecnica/issues/5)).

## Hitos

| Hito | Fecha | Entregable |
| :--- | :--- | :--- |
| [0 · Entorno y seguridad](https://github.com/tinioviedo/base-tecnica/milestone/1) | Semana del 2 nov | Repo desde la plantilla, pipeline en verde con Trivy y SonarQube |
| [1 · Implementación inicial](https://github.com/tinioviedo/base-tecnica/milestone/2) | 13 nov | Contrato publicado y endpoints respondiendo con mocks |
| [2 · Refinamiento y calidad](https://github.com/tinioviedo/base-tecnica/milestone/3) | 4 dic | Lógica real en PostgreSQL y umbrales de Trivy y SonarQube superados |
| [3 · Ensamblaje LPS](https://github.com/tinioviedo/base-tecnica/milestone/4) | 21 dic | APIs y microcomponentes listos para componer; presentación de la derivación |
| [4 · Cierre](https://github.com/tinioviedo/base-tecnica/milestone/5) | 11 ene | Validación con clientes y notas finales |

## Registro de servicios

Paquetes de la base común y sus dependencias. Todos validan la sesión con el JWKS de la Base técnica.

| Paquete | Grupo | Depende de | N / puertos (web, api) | Contrato |
| :--- | :--- | :--- | :--- | :--- |
| Productos | 3 | — | por asignar | pendiente |
| Stock | 8 | Productos | por asignar | pendiente |
| Catálogo | 2 | Productos, Stock | por asignar | pendiente |
| Registro de venta | 9 | Productos, Stock | por asignar | pendiente |
| Boleta y anulación | 1 | Stock, Registro de venta | por asignar | pendiente |
| Historial e inventario | 4 | Stock, Registro de venta | por asignar | pendiente |
| Ranking y rentabilidad | 5 | Productos, Registro de venta | por asignar | pendiente |
| IVA y exportación | 7 | Registro de venta | por asignar | pendiente |
| **Base técnica** | **6** | — | por asignar | pendiente |

Cada servicio usa los puertos locales `51N0` (web) y `51N1` (api) según su número N.

## Convenciones

- `main` protegida. El trabajo va en ramas `feat/<tema>` o `fix/<tema>`.
- Merge solo por PR, con al menos una aprobación de otra persona del grupo y los checks `calidad`,
  `seguridad` e `imagen` en verde.
- Commits con Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`).
- Identificadores y comentarios en español. Endpoints en español y en plural (`/api/usuarios`).

## Por definir con el jefe de proyecto

- [ ] Organización de GitHub del curso (`<org>` para GHCR y GitHub Packages)
- [ ] Número N del servicio
- [ ] URL de la instancia SonarQube del curso (`SONAR_HOST_URL`); la clave del proyecto es
  `base-tecnica-grupo6` ([#6](https://github.com/tinioviedo/base-tecnica/issues/6))
