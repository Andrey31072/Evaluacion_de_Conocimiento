# ADR-005 - Contenerización de PostgreSQL y Liquibase (Docker)

**Título:** ADR-005 - Proponer contenedorización completa con Docker Compose (PostgreSQL + Liquibase)

**Contexto:**
Necesidad de un entorno local reproducible e idéntico entre desarrolladores y entornos de prueba.

**Problema:**
Sin contenedores, cada desarrollador debe instalar PostgreSQL manualmente, generando inconsistencias.

**Decisión:**
Crear docker/docker-compose.yml con dos servicios:
- postgres (base de datos)
- liquibase (aplicación de migraciones)

**Justificación técnica:**
- Un solo comando docker compose up -d levanta todo el ambiente.
- Volúmenes persistentes y healthchecks incluidos.
- Compatible con futuros entornos QA/Producción (Kubernetes o Docker Swarm).

**Consecuencias / Impacto esperado:**
- Entorno 100% reproducible.
- Facilita la integración de Liquibase.
- Mejora la experiencia de desarrollo y reduce errores de configuración.