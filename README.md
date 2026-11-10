VIPIS - Dashboard de Monitoreo Ambiental e Inteligencia Artificial

Sistema IoT y MLOps para la Vía Parque Isla de Salamanca

Este repositorio contiene el código fuente del frontend web (Dashboard) del proyecto VIPIS, una solución integral desarrollada para el monitoreo ambiental en tiempo real, control de actuadores en la nube y clasificación de la calidad del aire mediante doble modelo de Inteligencia Artificial.

🚀 Características Principales del Dashboard

El panel web está diseñado con un estilo moderno, responsivo y adaptativo, integrando los siguientes módulos clave:

Telemetría Ambiental en Tiempo Real:

Visualización dinámica de gráficas y medidores (gauges) conectados al canal público de ThingSpeak (Channel ID: 3541323), monitoreando variables críticas: eCO₂ (Dióxido de carbono equivalente), TVOC (Compuestos Orgánicos Volátiles), Temperatura y Humedad Relativa.

Control Remoto de Actuadores (LED Cloud Control):

Panel interactivo para encender o apagar de forma remota el LED físico conectado al dispositivo ESP32. La orden se comunica a través de una API REST alojada en Render con persistencia en Neon PostgreSQL.

Modelo 1: Árbol de Decisión en la Nube (API Render):

Formulario interactivo conectado al backend oficial de la API (/api/ml/predecir).

Envía los valores de temperatura, humedad, eCO₂ y TVOC para ser clasificados en tiempo real (Buena, Moderada, Mala) por un modelo de Árbol de Decisión entrenado con scikit-learn (100% de Accuracy) y serializado en formato .pkl.

Modelo 2: Edge Impulse (IA Local WebAssembly):

Formulario secundario que ejecuta una red neuronal localmente en el navegador mediante WebAssembly, permitiendo realizar inferencias directamente en el cliente sin depender de llamadas al servidor.

Asistente IA Flotante (Chatbot):

Widget interactivo en la esquina inferior derecha impulsado por Google Gemini con respaldo local, capaz de responder consultas sobre el estado del sistema, estadísticas y ejecutar órdenes de control por lenguaje natural.

🛠️ Tecnologías y Librerías Utilizadas

Estructura: HTML5 semántico y CSS3 moderno (con variables CSS y diseño adaptativo).

Tipografía: Plus Jakarta Sans (Google Fonts).

Telemetría: ThingSpeak Widgets & Charts API.

Inteligencia Artificial:

Cloud MLOps: FastAPI + scikit-learn (Árbol de Decisión).

Edge AI: Edge Impulse Standalone (WebAssembly).

Hosting: GitHub Pages.

📂 Estructura de Archivos del Repositorio

├── index.html                  # Archivo principal del dashboard
├── edge-impulse-standalone.js  # Motor WebAssembly de Edge Impulse
├── run-impulse.js              # Lógica de ejecución del modelo local
└── README.md                   # Documentación técnica del proyecto


🌐 Enlaces del Proyecto

Backend / API (Render): https://vipis-air-quality-api.onrender.com

Dataset de Entrenamiento (Kaggle): Indoor Air Quality Monitoring Dataset
