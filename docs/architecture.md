# Arquitectura del proyecto

Batalla Urbana está construido siguiendo una arquitectura hexagonal, separando la lógica del juego de la infraestructura y los frameworks.

## Capas principales

### Dominio
Contiene las reglas del juego:
- Turnos
- Rondas
- Habilidades
- Validaciones de acciones

La lógica del dominio no depende de Spring ni de WebSockets.

### Aplicación
Orquesta los casos de uso del juego:
- Crear sala
- Unirse a partida
- Ejecutar acción
- Cambiar turno o ronda

### Adaptadores
Permiten la comunicación con el exterior:
- WebSockets como adaptador de entrada
- Infraestructura y configuración como adaptadores de salida

## Beneficios
- Código más mantenible
- Lógica desacoplada
- Facilidad para testing y evolución
