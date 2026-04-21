# ADR-003 - Implementar Liquibase para el versionamiento del DDL

**Contexto**
El DDL actual es un único archivo grande (modelo_postgresql.sql).

**Problema**
Imposible controlar cambios, hacer rollback o desplegar de forma ordenada en entornos dev/qa/prod.

**Decisión**
Adoptar Liquibase con:
- changelog-master.xml
- Un changelog por dominio funcional (máximo un archivo por dominio).

**Justificación técnica**
- Liquibase es el estándar para PostgreSQL en proyectos profesionales.
- Permite migraciones controladas, reproducibles y auditables.
- Cumple con la regla explícita del instrumento de evaluación.

**Consecuencias y Impacto esperado**
- Cambios versionados y seguros.
- Fácil integración con Docker y CI/CD.