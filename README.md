# Ecosistema de Automatización IA Autónomo para Negocios (HITL)

Proyecto Final de la materia **IA Automation**. Sistema de extremo a extremo que automatiza el análisis, scoring comercial y redacción de propuestas personalizadas para clientes B2B, integrando un punto de pausa mandatorio con validación humana (*Human-in-the-Loop*).

## 🚀 Stack de Tecnologías
* **Orquestador:** n8n Cloud
* **Base de Datos:** Airtable (Arquitectura Relacional)
* **Motor Cognitivo:** Google Gemini 1.5 Flash (Inferencia Estructurada JSON)
* **Canal de Notificación Interna:** Slack API (Bot interactivo en canal de revisión)
* **Canal de Distribución:** Gmail API

## 🔗 Enlaces del Proyecto
* **Base de Datos Airtable (Modo Lectura):** [PEGA_AQUÍ_TU_ENLACE_PÚBLICO_DE_AIRTABLE]
* **Video Demo (3 minutos):** [PEGA_AQUÍ_TU_ENLACE_A_LOOM_O_YOUTUBE]

## 🛠️ Arquitectura y Flujo de Trabajo
1. **Ingesta:** Filtrado de registros en Airtable con estado `Nuevo`.
2. **Contextualización RAG:** Búsqueda referencial en la tabla relacional `Servicios`.
3. **Inferencia Cognitiva:** Asignación de score (0-100) y redacción ejecutiva en JSON por Gemini.
4. **Registro:** Persistencia de borrador en Airtable con estado `Esperando Aprobacion`.
5. **Notificación:** Alerta contextual enviada a Slack para revisión del equipo comercial.
6. **HITL (Human-in-the-Loop):** Nodo `Wait` configurado para retener la ejecución hasta recibir el trigger del supervisor.
7. **Distribución Condicional:** Nodo condicional `If` que verifica la aprobación antes de ejecutar la acción crítica.
8. **Salida Multicanal:** Envío del correo formal vía Gmail y actualización del registro en Airtable a `Enviado al Cliente`.

## 📁 Estructura del Repositorio
* `diagrama_arquitectura.pdf`: Memoria técnica detallada y diagramas.
* `workflow_ecosistema.json`: Archivo exportado del flujo en n8n listo para importar.
* `/evidencias/`: Capturas de pantalla de la ejecución completa en verde, configuración de nodos, alertas y entrega multicanal.
