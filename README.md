# 🎸 Arpeg.io

*Aplicación nativa para Android que soluciona la fragmentación en el estudio musical, ofreciendo un entorno unificado interactivo.*

## 📝 Descripción
Arpeg.io es un proyecto desarrollado como Trabajo de Fin de Grado (TFG) para el ciclo de Desarrollo de Aplicaciones Multiplataforma (DAM). Su objetivo principal es facilitar el aprendizaje musical permitiendo a los músicos visualizar tablaturas interactivas (en formatos estándar como Guitar Pro) sincronizadas en tiempo real con la reproducción de su referencia auditiva original.

## ✨ Características Principales
- **Sincronización Precisa:** Desplazamiento automático de la tablatura ajustado milimétricamente al audio mediante la API de YouTube.
- **Catálogo Híbrido:** Acceso a una biblioteca compartida en la nube y gestión de archivos locales.
- **Reproductor Local Avanzado:** Motor de reproducción offline con control de velocidad (BPM) y metrónomo visual/sonoro.
- **Soporte Multi-Instrumento:** Cambio dinámico entre las distintas pistas (guitarra, bajo, batería, etc.) de una misma partitura.

## 🛠️ Stack Tecnológico y Arquitectura
El proyecto sigue los principios de **Clean Architecture** estructurándose bajo el patrón **MVVM** (Model-View-ViewModel), separando claramente la lógica de negocio, la gestión de estado y la interfaz de usuario.

- **UI:** Interfaz completamente declarativa construida con **Jetpack Compose** y flujos reactivos (`StateFlow`).
- **Asincronía:** **Kotlin Coroutines** para la gestión concurrente de flujos de datos sin bloquear el hilo principal.
- **Datos y Persistencia:**
  - **Firebase Firestore:** Base de datos NoSQL para gestionar en tiempo real el catálogo colaborativo en la nube.
  - **Room (SQLite):** Persistencia local para almacenar partituras del usuario y permitir su funcionamiento sin conexión.
- **Herramientas de Renderizado:** Integración de la librería **AlphaTab** sobre un entorno Web embebido para el dibujo e interacción de las partituras.

## 🧪 Testing y Calidad de Código
El proyecto cuenta con un entorno de pruebas robusto diseñado para garantizar la estabilidad de la lógica de negocio y los flujos de datos.

- **Pruebas Unitarias:** Implementadas con **JUnit**, utilizando **Mockito** para generar dobles de prueba y aislar el repositorio (evitando dependencias directas con Firestore o Room).
- **Testeo Asíncrono:** Uso de reglas personalizadas con `UnconfinedTestDispatcher` para forzar la ejecución síncrona de las corrutinas durante los tests.
- **Cobertura con JaCoCo:** El análisis de calidad del código está estrictamente configurado. Las pruebas base que Java y Android incorporan por defecto no se toman en cuenta para evitar inflar las métricas de forma artificial. El porcentaje de cobertura mínima aceptable está definido manualmente de forma exigente, asegurando la validación de la lógica real tras filtrar clases autogeneradas.

## 🚀 Instalación y Uso
1. Clona el repositorio en tu máquina local:
   ```bash
   git clone [https://github.com/Megadeftro17/Arpeg.io.git](https://github.com/Megadeftro17/Arpeg.io.git)
