# GPX Tracker PWA

Aplicación web progresiva (PWA) de alto rendimiento diseñada para la navegación y seguimiento de rutas GPX en entornos exteriores. Desarrollada para operar en dispositivos móviles Android con optimización para visibilidad bajo luz solar directa y funcionamiento en zonas con conectividad intermitente o nula, accesible desde https://diegomguillen.github.io/outdoor_navigator/

## Descripción General

Este software permite la carga y visualización de archivos de trazado `.gpx` sobre mapas base intercambiables (OpenStreetMap y Satélite). Su funcionalidad principal reside en la capacidad de determinar algorítmicamente el sentido de la marcha del usuario respecto a la ruta cargada, indicando en tiempo real si el desplazamiento es correcto ("Adelante") o inverso ("Revés").

La aplicación está construida bajo la arquitectura de *Single Page Application* (SPA) y cumple los estándares de PWA para permitir su instalación nativa en el sistema operativo Android, garantizando el acceso a APIs críticas como Geolocalización de Alta Precisión y *Screen Wake Lock*.

## Características Principales

* **Motor de Renderizado:** Integración de Leaflet.js para visualización de mapas raster (OSM) e imágenes satelitales (Esri World Imagery).
* **Interfaz de Alto Contraste:** Paleta de colores industrial (Amarillo Seguridad/Negro y Azul/Blanco) diseñada para máxima legibilidad en exteriores.
* **Cálculo Vectorial de Dirección:** Algoritmo matemático basado en el producto escalar para determinar la alineación del usuario con la tangente de la ruta.
* **Persistencia Local:** Almacenamiento de rutas en `localStorage` y caché de recursos mediante *Service Workers* para funcionamiento *offline*.
* **Gestión de Energía:** Implementación de la API *Screen Wake Lock* para evitar el bloqueo automático de la pantalla durante la navegación.
* **Controles Ergonómicos:** Botonera inferior dimensionada para manipulación táctil en movimiento.

## Estructura del Proyecto

Para el correcto despliegue de la aplicación, el directorio raíz debe contener los siguientes archivos:

```text
/
├── index.html       # Núcleo de la aplicación (Lógica UI, Mapa y Algoritmos)
├── manifest.json    # Manifiesto de metadatos para instalación PWA Android
├── sw.js            # Service Worker (Gestión de caché y offline)
└── icon.png         # Icono de la aplicación (Resolución recomendada: 512x512px)
