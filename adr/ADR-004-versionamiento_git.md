# ADR-004 - Estrategia de versionamiento del Repositorio (Git Flow Simplificado)


**Contexto:**
Se necesita trabajo pararelo y entornos estables (Desarrollo, pruebas y producción)

**Decesión:**
Usar tres ramas (Ambientes) principales:

- dev -> Desarrollo activo
- qa -> Pruebas de aceptació
- main -> Producción (Solo se llegara medianto merge desde HU-MAIN)

**Justificación Tecnica:**
- Flujo probado y compatible con liquibase y docker.
- main nunca se toca direcmente (Solo mediante las historias de usuarios y claramente los merges), evitando asi que errores lleguen directamente producción.

**Consecuencia y Impacto esperado:**
- Reglas claras de merge y proteccion de ramas.
