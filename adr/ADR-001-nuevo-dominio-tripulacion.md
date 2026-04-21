# ADR-001 - Ampliación de un nuevo dominio funcional - Crew Management (Gestión de Tripulación)

**Contexto**
El modelo actual cubre aeronaves, vuelos, pasajeros y fidelización, pero no existe ninguna tabla relacionada con la tripulación (pilotos, copilotos, auxiliares de vuelo).

**Problema**
No es posible asignar tripulantes a vuelos, controlar certificaciones, horas de vuelo ni cumplir con regulaciones de seguridad operativa.

**Decisión**
Crear un nuevo dominio funcional llamado "crew" con las tablas:

- crew_member
- crew_role
- crew_assignment
- crew_certification

**Justificación técnica**
- Mantiene la misma arquitectura (UUID, restricciones CHECK, índices).
- Se integra fácilmente con `flight_segment` y `aircraft`.
- Cumple con la regla de "un dominio = un changelog" de Liquibase.

**Consecuencias / Impacto esperado**
- +4 tablas nuevas.
- Mejora trazabilidad operativa y seguridad.
- Próximo changelog: `changelogs/013-crew.xml`.