# Batalla Urbana — Juego web multijugador en tiempo real

**Batalla Urbana** es un juego web multijugador en tiempo real, basado en **turnos y rondas**, con **habilidades de personajes** y lógica de juego validada completamente en el servidor.

El backend es **server-authoritative**: el servidor decide qué acciones son válidas (turnos, rondas y habilidades) y los clientes reciben los eventos en tiempo real mediante **WebSockets (STOMP)**.

---

## Tecnologías
- **Backend**: Java + Spring Boot  
  - Arquitectura Hexagonal  
  - WebSockets (STOMP)
- **Frontend**: React + Tailwind
- **Comunicación**: Tiempo real mediante WebSockets

Repositorios:
- Backend: https://github.com/sauldm/batalla-urbana-back
- Frontend: https://github.com/sauldm/batalla-urbana-front

---

## Demo online (Live)
- **https://www.batallaurbana.com/**

### Cómo probar el multijugador
1. Abre la web en una ventana normal (Jugador 1)
2. Abre la misma web en una ventana **Incógnito** o en otro navegador (Jugador 2)
3. Crea una sala → únete → inicia la partida → juega un turno

---

## Funcionalidades principales
- Multijugador en tiempo real
- Flujo completo: **sala → partida → turnos → rondas**
- Habilidades de personajes
- Indicador de turno y estado de la partida
- Validación de acciones en servidor (no se puede jugar fuera de turno)
- Arquitectura hexagonal con dominio desacoplado

---

## Arquitectura
El proyecto sigue una **arquitectura hexagonal**, separando claramente la lógica del juego de la infraestructura.

- **Domain**  
  Reglas del juego: turnos, rondas, habilidades y validaciones.
- **Application**  
  Casos de uso que orquestan la lógica del dominio.
- **Adapters (in / out)**  
  Entrada mediante WebSockets e infraestructura del sistema.

Esta separación permite un código más mantenible, testeable y escalable.

---

## Ejecutar en local

### Backend
```bash
git clone https://github.com/sauldm/batalla-urbana-back
cd batalla-urbana-back
mvn clean spring-boot:run
```
- Disponible en: http://localhost:8080
### Frontend
```bash
git clone https://github.com/sauldm/batalla-urbana-front
cd batalla-urbana-front
npm install
npm run dev
```
- Disponible en: http://localhost:5173

---

## Roadmap (mejoras futuras)

- Reconexión de jugadores si se pierde la conexión
- Persistencia de partidas
- Matchmaking automático
- Métricas y logs para monitorizar partidas



