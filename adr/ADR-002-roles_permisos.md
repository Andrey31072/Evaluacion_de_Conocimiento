# ADR-002 - Manejo de roles con permisos diferenciados (RBAC completo)

**Contexto**
Ya existen las tablas security_role, security_permission, user_role y role_permission.

**Problema**  
Falta trazabilidad de quién asignó/quitará el rol y no hay auditoría de cambios de permisos.

**Decisión**
Ampliar la tabla user_role agregando:
- assigned_by_user_id
- revoked_at

Crear vistas/materialized views para "permisos efectivos del usuario".

**Justificación técnica**
- RBAC completo + trazabilidad sin romper 3FN.
- Compatible con el modelo de seguridad existente.
- Facilita auditoría y cumplimiento normativo.

**Consecuencias y Impacto esperado**
- Mayor seguridad y control de accesos.
- Posibilidad de implementar "quién y cuándo" en cada asignación de rol.