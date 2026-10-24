# Sistema de control y automatización para planta de producción de etanol

Proyecto final de la materia **Gestión de proyectos de software (ISC502)**, Licenciatura en Ingeniería en Sistemas Computacionales, 5.º semestre.

- **Alumno:** Kevin Xavier Vergara Caicero
- **Docente:** LI. Nora Isela Zamora Aguilar
- **Fecha:** octubre de 2026

## Descripción

En la producción de etanol, variables como la temperatura y la concentración de etanol deben mantenerse en rango. Cuando el control depende del criterio del operador y de ajustes manuales, aparecen variabilidad entre lotes, desviaciones y detección tardía de fallas.

Este proyecto diseña un sistema de software que adquiere datos del proceso en tiempo real (OPC UA), restringe sus funciones por rol, regula automáticamente la concentración con setpoints estandarizados y emite alertas preventivas mediante una función inteligente basada en reglas.

> Es un proyecto de **diseño**: el prototipo es de baja fidelidad y no funcional.

## Usuarios

| Rol | Qué hace |
| --- | --- |
| Operador manual | Ve las variables, ajusta la temperatura (28–35 °C) y acciona actuadores. |
| Supervisor | Define setpoints estandarizados, revisa tendencias, alarmas y bitácora. |

## Requerimientos

| ID | Resumen |
| --- | --- |
| RF01 | Inicio de sesión con correo, contraseña y rol; muestra la pantalla del rol. |
| RF02 | El Operador manual ajusta la temperatura entre 28 °C y 35 °C y presiona «Aplicar». |
| RF03 | En modo automático, lectura de S-101 cada 5 s y corrección si la desviación supera 0.5 % v/v. |
| RNF01 | Corrección en menos de 1 s; tablero actualizado cada 5 s. |
| RNF02 | Control de acceso por rol (RBAC) y contraseñas cifradas (NIST SP 800-82). |
| RD01–RD03 | Entidades: Usuario, Lectura de proceso y Evento. |

## Función inteligente

Reglas sencillas (no es un modelo de IA) que usan el promedio móvil de las últimas 6 lecturas de los sensores T-101 y S-101 y la tasa de cambio de la concentración, para generar alertas y recomendaciones preventivas (reglas R1 a R5).

## Prototipo

Cuatro pantallas: inicio de sesión, panel del Operador manual, panel automático del Supervisor, y centro de alarmas con recomendación inteligente.

```

## Gestión del proyecto

- Tablero de 10 tareas con prioridad, estimación y estado.
- 3 riesgos identificados con su mitigación.
- Validación con la lista de cotejo de requerimientos (ISO/IEC/IEEE 29148:2018) y revisión grupal, con mejoras documentadas.

## Control de versiones

El historial de commits registra los hitos del proyecto: inicio, requerimientos, alcance, prototipo y versión final.

## Referencias

- ISO/IEC/IEEE 29148:2018. *Systems and software engineering — Life cycle processes — Requirements engineering.*
- NIST SP 800-82. *Guide to Operational Technology (OT) Security.*
- OPC Foundation. *OPC Unified Architecture (OPC UA).*
