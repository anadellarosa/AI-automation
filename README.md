# Sistema de contenido con IA para un estudio contable (Entrega Final · AI Automation)

Pipeline de automatización para community managers: la IA redacta los textos de cada pieza de redes sociales a partir de la ficha estratégica del cliente, y una persona aprueba antes de que algo avance. MVP con un cliente: Estudio Contable Cerro-Colombo (Santiago del Estero).

## Cómo funciona

- **Flujo B (generación):** al pasar una pieza a "Generar", n8n consulta la base de conocimiento del cliente, Claude redacta el texto y la pieza queda en "Para revisar".
- **Flujo B2 (aprobación):** cuando la persona tilda "Aprobado" y el texto está completo, la pieza pasa a "Listo para publicar". Si hay datos sin confirmar, vuelve a "Revisión manual".
- **Errores:** reintentos, estado "Error", registro en Log errores y aviso por Telegram.

## Tecnología

| Categoría | Herramienta |
| --- | --- |
| Orquestador | n8n (Docker) |
| Base de datos | Airtable (control) y Notion (base de conocimiento) |
| IA | Claude Sonnet 5.5 |
| Canal de salida | Telegram |

## Estructura del repositorio

| Carpeta | Contenido |
| --- | --- |
| `01-diagrama/` | Diagrama de arquitectura (PDF) |
| `02-manual-datos/` | Manual de datos con Omni AI y JSON (PDF) |
| `03-matriz-costos/` | Matriz de costos (PDF) |
| `04-seguridad-resiliencia/` | Seguridad y resiliencia (PDF) |
| `05-dashboard/` | Enlaces al dashboard público (README) |
| `flujos/` | JSON de los workflows de n8n (sin claves; instanceId y chatId redactados) |
| `capturas/` | Capturas de ejecuciones, tablas y pruebas |

## Seguridad

Ninguna clave se guarda en el repositorio: las credenciales viven en n8n. Los JSON se revisaron antes de subirse (sin claves ni emails) y se reemplazaron el identificador de instalación y el chat ID.

## Evidencia

- Dashboard público: ver `05-dashboard/README.md`.
- Video demo de 3 minutos: PENDIENTE (enlace).
- Prueba de estrés: ejecuciones y piezas en `capturas/`.
