# REGLAS Y CONTEXTO DEL PROYECTO (MEMORIA MAESTRA)

## 1. Arquitectura General
- **Interfaz (Frontend):** Repositorio Coucou (`Louis-CFM/coucou`), rama activa: `feature/roles-mochis`.
- **Cerebro (Backend):** Servidor externo en Oracle ejecutando agentes en Python (FastAPI).
- **Mapeo de agentes:** La interfaz lee `config_agentes.json` para saber a qué endpoint enviar cada mensaje. Coucou NO ejecuta lógica pesada internamente.

## 2. Roles Asignados a los Mochis
- **Mochi Blanco:** Asistente principal y chatbot general (`/agente/blanco`).
- **Mochi Verde:** Gestor de redes sociales y automatización (`/agente/verde`).
- **Mochi Azul:** Analista de métricas y datos (`/agente/azul`).
- **Mochi Rojo:** Tareas pesadas de investigación y scraping en background (`/agente/rojo`).

## 3. Reglas Estrictas de Desarrollo
1. **Principio de no regresión:** No modificar animaciones, layouts ni el ciclo de vida base de Coucou para mantener compatibilidad con actualizaciones upstream.
2. **Modularidad:** Modificar únicamente el archivo específico asignado a la tarea. No refactorizar archivos adyacentes por cuenta propia.
3. **Seguridad:** Nunca colocar claves privadas ni IPs directamente en código; usar siempre `.env` y mantenerlo ignorado en Git.
4. **Validación previa:** Explicar el cambio en español simple y mostrar el diff antes de tocar archivos.
5. **Actualización de memoria:** Cada vez que completemos una tarea con éxito, actualizar la sección 4 de este archivo antes de cerrar el chat.

## 4. Estado Actual del Proyecto y Avances (Bitácora)
- [x] Repositorio vinculado al fork personal en GitHub con upstream al creador original.
- [x] Rama `feature/roles-mochis` creada y activa.
- [x] Archivos `.env` y `.gitignore` configurados con seguridad.
- [x] Archivo `config_agentes.json` creado en la raíz.
- [x] Inspeccionar y localizar el archivo de Coucou encargado de enviar los mensajes del chat (`ClaudeService.swift`).
- [x] Conectar ese archivo con `config_agentes.json` para despachar según el Mochi seleccionado.
- [ ] Backend modular levantado en Oracle con los 4 endpoints aislados.
