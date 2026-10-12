# entorno-ejemplo

Entorno de trabajo para agentes de programación, generado con **meta-harness** el 2026-10-12.
Es **independiente**: no necesita el meta-harness para funcionar ni para actualizarse. Lo que contiene es tuyo.

## Qué trae (módulos elegidos)

- **documentacion-primero**: Documentación antes que código y datos; buscador y recordatorio automático
- **compuerta-calidad**: Compuerta antes de entregar (tus comandos + secretos) y aviso antes de commitear
- **conocimiento**: Índice del conocimiento y control de frescura de los documentos
- **escaneo-secretos**: Escaneo de claves, tokens y credenciales en lo versionado
- **autoguardado**: Commit automático al cerrar la sesión (subida opcional y desactivada por defecto)
- **publicar-solo-verificado**: Nada se publica (PR, comentario, nota de versión) sin verificar el texto contra sus fuentes
- **bloqueo-datos**: El agente no escribe en bases de datos ni se conecta a ambientes que no son locales (barrera, no garantía)
- **formato-de-pr**: Un PR no se crea sin las secciones que exige su tipo (pase a producción, observaciones...), según tus tipos declarados
- **inventario-de-fuentes**: Foto de los repositorios antes de analizar: contra qué rama de referencia se compara y líneas de sello para pegar
- **sello-de-verificacion**: Los sellos `verificado-contra-git` de los documentos caducan: se revisan contra la rama de referencia
- **aprendizaje**: Lecciones con evidencia: no hay regla sin evidencia y toda regla se revierte

## Cómo se usa

1. `./instalar.sh` muestra qué hace falta en tu máquina (solo lee) y `./instalar.sh --aplicar` deja el repo listo.
2. Abre esta carpeta con tu agente. Claude Code carga `.claude/settings.json` y activa los hooks; Codex lee `AGENTS.md`.
3. `./verificar.sh` comprueba que el entorno está sano. `./scripts/gate.sh` es la compuerta antes de entregar.

## Cómo se cambia

Todo está en `entorno.toml` (módulos, comandos de la compuerta, rutas de documentación, autoguardado). Cada script es de
lectura corta y se puede editar. Las reglas aprendidas con evidencia se promueven con `scripts/aprender.py` y se pueden revertir.

Licencia Apache-2.0 (ver `LICENSE` y `NOTICE`). Origen y qué se copió: `docs/ORIGEN.md`.
