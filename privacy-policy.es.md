# Política de Privacidad — delphi-ag-dev

> 🇺🇸 [English](privacy-policy.md) · 🇧🇷 [Português](privacy-policy.pt-BR.md) · 🇪🇸 [Español](privacy-policy.es.md)

**Última actualización:** Abril de 2026

---

## Descripción general

**delphi-ag-dev** es un plugin de código abierto para el sistema de IA multi-agente [Antigravity](https://github.com/mrschuster1/delphi-ag-dev). Este documento explica qué datos procesa el plugin, cómo se tratan y tus derechos como usuario.

---

## Qué datos procesa el plugin

El plugin **delphi-ag-dev** opera completamente dentro del contexto de tu entorno de desarrollo local y de la sesión del agente de IA. **No** tiene ningún servicio de backend, base de datos ni API externa propia.

El plugin puede procesar los siguientes tipos de datos **únicamente dentro de tu sesión de IA**:

| Tipo de dato | Propósito | ¿Almacenado externamente? |
|---|---|---|
| Archivos de código fuente (`.pas`, `.dfm`, etc.) | Revisión de código, auditoría, generación de tests | ❌ No |
| Nombres y estructura de archivos del proyecto | Generación de Spec, análisis de arquitectura | ❌ No |
| Descripciones en lenguaje natural que proporcionas | Generación de nuevo código con `/delphi-write` | ❌ No |

---

## Cómo se tratan los datos

- Todo el procesamiento de datos ocurre **localmente dentro de tu sesión del agente de IA**.
- El plugin **no** envía, almacena ni transmite ningún código fuente o dato de tu proyecto a servidores externos.
- Los únicos datos que salen de tu máquina son los enviados al **proveedor del modelo de IA** (ej: Anthropic, Google, etc.) como parte de la sesión normal de IA — regidos por sus propias políticas de privacidad.
- Este plugin es puramente una capa de configuración (Skills + Workflows) — no tiene código ejecutable, llamadas de red ni persistencia de datos propios.

---

## Proveedores de IA de terceros

Cuando interactúas con un agente de IA que tiene este plugin cargado, tus prompts y cualquier código que compartas son procesados por el proveedor del modelo de IA subyacente. Consulta sus políticas de privacidad:

- [Política de Privacidad de Anthropic](https://www.anthropic.com/privacy)
- [Política de Privacidad de Google](https://policies.google.com/privacy)

---

## Datos que compartes voluntariamente

Este es un proyecto de código abierto alojado en GitHub. Si:

- **Abres un issue** o **envías un pull request**, tu nombre de usuario de GitHub y el contenido que envíes estarán visibles públicamente en GitHub, sujeto a la [Política de Privacidad de GitHub](https://docs.github.com/es/site-policy/privacy-policies/github-privacy-statement).
- **Das una estrella o haces un fork** del repositorio, esta actividad también es pública en GitHub.

---

## Sin analíticas ni telemetría

**delphi-ag-dev** **no** recopila telemetría, estadísticas de uso ni datos analíticos. No existe ningún tipo de seguimiento.

---

## Privacidad de menores

Este plugin está destinado al uso por parte de desarrolladores de software. No está diseñado para, ni procesa conscientemente datos de, niños menores de 13 años.

---

## Cambios en esta política

Esta política de privacidad puede actualizarse periódicamente. Los cambios se reflejarán en la fecha de "Última actualización" en la parte superior de este documento. El uso continuado del plugin tras los cambios constituye la aceptación de la política actualizada.

---

## Contacto

Para preguntas o inquietudes sobre esta política de privacidad, abre un issue en el repositorio de GitHub:

👉 [https://github.com/mrschuster1/delphi-ag-dev/issues](https://github.com/mrschuster1/delphi-ag-dev/issues)
