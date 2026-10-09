# ADR-001: Adopción del estilo arquitectónico en capas

- **Estado:** Propuesto
- **Contexto:** Entregable 03, sistema web de gestión de emergencias del Hospital Regional de Ayacucho
- **Fecha:** 2026-10-08

## Contexto

El sistema necesita módulos de admisión, triaje, atención médica y administración, con persistencia e integraciones potenciales. El equipo requiere una propuesta inicial sencilla de implementar, probar y mantener.

## Decisión

Adoptar **arquitectura en capas**, con Angular como aplicación cliente, ASP.NET Core Web API como servidor, casos de uso, dominio, adaptadores de infraestructura y PostgreSQL. El backend se desplegará inicialmente como un **monolito modular**.

## Alternativas consideradas

- Microservicios: mayor complejidad operacional y consistencia distribuida sin evidencia de necesidad inicial.
- Monolito sin separación lógica: menor estructura y mayor riesgo de dependencias cruzadas.

## Consecuencias

**Positivas:** responsabilidades claras, evolución progresiva, facilidad para incorporar pruebas y controles transversales.  
**Negativas:** exige disciplina en la dirección de dependencias; el despliegue centralizado puede requerir modularización posterior si aparecen requisitos de escalado independiente.

## Validación futura

Revisar el diseño con escenarios de seguridad, interoperabilidad, tiempos de respuesta y disponibilidad institucionales.
