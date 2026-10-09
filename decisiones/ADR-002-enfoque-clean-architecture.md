# ADR-002: Uso de Clean Architecture en el backend

- **Estado:** Propuesto
- **Contexto:** Entregable 03, sistema web de gestión de emergencias del Hospital Regional de Ayacucho
- **Fecha:** 2026-10-08

## Contexto

La persistencia y las integraciones de identidad/seguro/historia clínica son detalles externos que pueden cambiar o no estar disponibles al iniciar el desarrollo. Las reglas de admisión y de gestión de una emergencia no deben estar acopladas a esos proveedores.

## Decisión

Dividir el backend en `Emergency.Domain`, `Emergency.Application`, `Emergency.Infrastructure` y `Emergency.Api`, con **dependencias de código hacia el núcleo**: Application depende de Domain; Infrastructure depende de Application/Domain; Api depende de Application y registra Infrastructure en la composición de dependencias.

## Consecuencias

**Positivas:** reglas testeables, integraciones reemplazables, menor acoplamiento con PostgreSQL y proveedores externos.  
**Negativas:** más clases, interfaces y configuración respecto de un CRUD sencillo; se debe evitar crear abstracciones innecesarias.

## Criterios de verificación

- Domain no referencia Infrastructure ni Api.
- Application no referencia Infrastructure.
- Los controladores no incluyen reglas de negocio complejas.
- Las integraciones externas se invocan desde Infrastructure mediante interfaces definidas en Application.
- Los casos de uso admiten pruebas unitarias sin una base de datos real.
