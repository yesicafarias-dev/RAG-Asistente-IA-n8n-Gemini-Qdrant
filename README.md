# RAG – Asistente IA con n8n, Gemini y Qdrant

Sistema de atención al cliente para **Colitas de Hilo**, desarrollado con n8n, Google Sheets, Gemini y Qdrant.

## Descripción

El proyecto utiliza RAG (*Retrieval-Augmented Generation*) para recuperar información de una base de conocimiento y generar respuestas a consultas de clientes.

## Workflows

### 1. Ingesta de conocimiento

Archivo: `RAG_Ingesta_PUBLICAR.json`

- Lee información desde Google Sheets.
- Genera identificadores UUID para los registros nuevos.
- Crea embeddings mediante Gemini.
- Almacena y actualiza los vectores en Qdrant.
- Procesa los registros mediante un bucle.

### 2. Recuperación y generación de respuestas

Archivo: `RAG_Retrieval_PUBLICAR.json`

- Recibe una consulta simulada.
- Genera un embedding de la consulta.
- Recupera información desde Qdrant.
- Construye un prompt con el contexto obtenido.
- Genera una respuesta mediante Gemini.
- Procesa la respuesta JSON con JavaScript.
- Clasifica las consultas como `AUTOMATICO` o `REVISION`.

## Tecnologías

- **n8n:** automatización de procesos.
- **Google Sheets:** almacenamiento de la base de conocimiento.
- **Gemini API:** embeddings y generación de respuestas.
- **Qdrant:** almacenamiento y búsqueda vectorial.
- **JavaScript:** procesamiento de respuestas.

## Estado del proyecto

**Prototipo funcional en desarrollo.**

La ingesta, recuperación, generación y clasificación de respuestas fueron probadas. La integración final con el CRM, el registro de consultas y el envío de mensajes están pendientes.

## Seguridad

Los workflows publicados fueron preparados para portfolio. Se eliminaron claves de API y datos privados. Para ejecutarlos es necesario configurar credenciales y recursos propios.
