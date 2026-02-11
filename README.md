Proyecto de Diseño de Software – Corte Uno
App Móvil de Arquitectura Asistida por IA (MVP)
Presentación del Problema

En el proceso de diseño arquitectónico, existe una brecha entre el boceto inicial y la validación técnica del uso del espacio. Muchas herramientas son complejas, no están pensadas para móvil o no ofrecen asistencia inteligente en tiempo real.

Nuestro proyecto propone una aplicación móvil con integración de Inteligencia Artificial que permite dibujar planos básicos y recibir sugerencias de optimización espacial. El sistema actúa como un asistente que analiza distribuciones y propone mejoras, facilitando decisiones tempranas de diseño.

Los principales beneficiarios son:

Estudiantes de arquitectura

Diseñadores de espacios

Usuarios que necesiten validar distribuciones básicas rápidamente desde móvil

Creatividad en la Presentación

Se presentará un video tipo demo donde se muestra:

Creación de un plano básico

Dibujo de muros y ventanas

Solicitud de optimización por IA

Respuesta del sistema con propuesta de distribución

🎥 Link del video: (poner aquí el enlace)

Fundamentos de Ingeniería de Software

El sistema prioriza los siguientes atributos de calidad:

Mantenibilidad: Arquitectura desacoplada usando interfaces y Strategy Pattern.

Escalabilidad: Permite cambiar o mejorar el motor de IA sin modificar la app móvil.

Flexibilidad: La terminal puede seleccionar diferentes estrategias de IA.

Modularidad: Separación clara entre núcleo de entidades, módulo de IA e interfaz móvil.

Diseño de Software
Principios SOLID aplicados

SRP — Single Responsibility Principle
Cada clase tiene una única responsabilidad:

Entidades (Plano, Muro, Ventana) solo representan estructura.

Clases de IA solo procesan análisis.

La app móvil solo gestiona interacción de usuario.

OCP — Open/Closed Principle
Se pueden agregar nuevas estrategias de IA sin modificar la app móvil, solo creando nuevas implementaciones de la interfaz de IA.

DIP — Dependency Inversion Principle
La aplicación móvil depende de la abstracción IAsistenteIA y no de una implementación concreta. Esto permite intercambiar motores de IA fácilmente.

Patrones de Diseño Utilizados

Strategy Pattern (Principal)
Se usa para encapsular diferentes algoritmos de análisis de IA.

Razón: Permite que la terminal móvil seleccione qué motor de IA usar.
Beneficio: Cambiar de modelo de IA no rompe la aplicación.

Ejemplo conceptual:

IAsistenteIA → IAOptimizadora → NuestraIA


Herencia + Abstracción (Modelo de Dominio)
Los elementos arquitectónicos heredan de una clase base abstracta.

ElementoArquitectonico (abstracto)
→ Muro
→ Ventana

Esto mejora reutilización y orden del modelo.

Diagrama UML

El sistema se divide en tres capas:

Núcleo de entidades (Proyecto, Plano, Elementos)

Módulo de IA (Strategy)

Terminal móvil (MVP)

📌 Diagrama UML: (poner imagen o enlace aquí — pueden usar la foto base que me mandaste como referencia formalizada)

Casos de Uso Principales

UC-01: Optimización de espacios
El usuario dibuja un plano y solicita optimización → la IA analiza y propone distribución.

UC-02: Gestión de elementos
Crear y editar muros y ventanas en el plano.

UC-03: Selección de motor de IA
La aplicación puede cambiar la estrategia de IA activa.

Implementación

El código se organiza en módulos:

/entidades
  Proyecto
  Plano
  ElementoArquitectonico (abstract)
  Muro
  Ventana

/ia
  IAsistenteIA (interface)
  IAOptimizadora
  NuestraIA

/app
  AppMovil


Relación clave:

AppMovil usa IAsistenteIA

NuestraIA implementa la estrategia activa

Plano contiene elementos arquitectónicos

Análisis Técnico

El sistema logra:

Alta cohesión:
Cada clase cumple una función específica (modelo, IA o interfaz).

Bajo acoplamiento:
Gracias al uso de interfaces y Strategy Pattern.

Extensibilidad:
Se pueden agregar:

Nuevos tipos de elementos

Nuevos motores de IA

Nuevas terminales (web, desktop)

Pruebas facilitadas:
El MVP puede probarse con mocks de IA mientras el modelo real se integra.

Créditos y Roles

(Editar con su equipo real)

Andrés — Arquitectura de software y patrones de diseño

Integrante 2 — Modelado UML

Integrante 3 — Implementación de entidades

Integrante 4 — Integración IA / pruebas

Integrante 5 — Video y presentación creativa
