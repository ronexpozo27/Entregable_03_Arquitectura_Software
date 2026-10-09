# ENTREGABLE 03 — Estilo arquitectónico y enfoque arquitectónico

**Proyecto:** Sistema Web para la Gestión de Atención de Emergencias del Hospital Regional de Ayacucho  
**Curso:** Laboratorio de Arquitectura de Software  
**Programa:** Ingeniería de Sistemas — UNSCH  
**Autor:** Ronex Pozo Sarmiento  
**Estado:** Propuesta inicial, sujeta a validación institucional y revisión del docente

## Propósito

Documentar el **estilo arquitectónico (arquitectura en capas)** y el **enfoque de diseño (Clean Architecture)** del sistema. Es una propuesta de diseño; **no** significa que las integraciones institucionales ya funcionen ni que exista una implementación desplegada.

## Archivos

- `ENTREGABLE-03.md`: informe integral, listo para revisar y ajustar.
- `diagramas/01-arquitectura-en-capas.mmd`: organización del sistema por capas y conexiones externas.
- `diagramas/02-clean-architecture.mmd`: dependencias previstas en el backend.
- `diagramas/03-flujo-emergencia.mmd`: flujo básico de admisión, triaje y atención.
- `decisiones/ADR-001-estilo-en-capas.md`: decisión arquitectónica de alto nivel.
- `decisiones/ADR-002-enfoque-clean-architecture.md`: decisión sobre responsabilidades y dependencias.

## Cómo abrir en Visual Studio Code

1. Abrir la carpeta `ENTREGABLE-03` en VS Code.
2. Abrir `ENTREGABLE-03.md` y ejecutar **Ctrl+Shift+V** para la vista previa de Markdown.
3. Los diagramas Mermaid se encuentran también embebidos en el documento principal; si tu vista previa no los dibuja, instala una extensión de visualización de Mermaid para VS Code.
4. Revisar la propuesta según la rúbrica y las indicaciones del docente.

## Criterio de diseño

Se elige una **aplicación web Angular (cliente) + una API ASP.NET Core modular (servidor)**, con PostgreSQL como persistencia y adaptadores de integración para servicios externos. No se propone microservicios para esta primera etapa porque aumentan los costes de operación y despliegue sin un requisito demostrado de escalado independiente.

## Nota de alcance

Las integraciones con RENIEC, SIS/seguros y servicios de historia clínica son **propuestas condicionadas** a permisos, disponibilidad de interfaces, acuerdos y requisitos normativos; no se deben representar como conexiones ya habilitadas.
