# Veintiuno

Juego de preguntas para jugar con amigos, cada uno desde su móvil. Cada pregunta tiene como respuesta un número del 0 al 10: vas pidiendo preguntas, sumas lo que crees que vale cada una y te plantas cuando creas que estás cerca de 21. Al final, el líder desvela las respuestas una a una y se ve quién se ha pasado.

- **Jugar:** https://ericrechevfx-cmyk.github.io/veintiuno/
- **Archivos:** `index.html` (el juego) y `preguntas.js` (el banco de preguntas).

No tiene servidor propio: los móviles se conectan entre sí (WebRTC) y usan el servidor gratuito de PeerJS solo para encontrarse, igual que The Mind.

## Cómo se juega

1. Uno pulsa **Crear sala**: le sale un código de 4 letras. Esa persona es el **líder**.
2. Los demás abren el enlace, ponen su nombre y el código. También pueden escanear el **código QR** del líder o abrir el enlace de **Invitar**.
3. El líder elige el modo y la dificultad, y pulsa **Empezar**.
4. En cada pregunta marcas cuánto crees que es (0 a 10) y eliges **Otra pregunta** o **Me planto**.
5. Cuando todos se han plantado, el líder pulsa **Siguiente** para desvelar las respuestas una a una.
6. Se juegan las rondas que queráis: los puntos se van sumando hasta que el líder pulsa **Terminar y ver la clasificación**.

### Modos

| Modo | Cómo funciona |
|---|---|
| Todos juntos | Todos reciben las mismas preguntas a la vez. Cada uno decide en secreto cuándo plantarse. |
| Cada uno | Cada jugador recibe sus propias preguntas y va a su ritmo. |
| Equipos | Igual que «Cada uno», pero cada móvil es un equipo. Al entrar se pone el nombre del equipo («Pepe y Juan»); en la sala se puede cambiar con **Cambiar nombre**. |

### Dificultad

| Nivel | Qué preguntas salen |
|---|---|
| Fácil | Sobre todo las que sabe casi todo el mundo. |
| Variada | Alguna fácil y muchas de las que te hacen dudar entre dos o tres números. |
| Difícil | Casi todas son datos que no sabes y tienes que deducir («¿cuántos presidentes del monte Rushmore llevan barba?»). |

Los puntitos de cada carta (●●○) indican la dificultad de esa pregunta.

### Puntos por ronda

- Tu suma si no pasas de 21.
- 21 exacto: 30 puntos.
- Si te pasas: 0.
- +2 por cada respuesta que clavas (aunque te pases).

## Cosas a tener en cuenta

- El móvil del líder es la "mesa": tiene que tener la página abierta. Si recarga, la partida sigue.
- Se puede entrar con la partida empezada: juegas desde la siguiente ronda.
- Si alguien se va a mitad de ronda, el líder puede tocar su nombre arriba y **plantarlo** para seguir.
- El móvil del líder recuerda qué preguntas han salido, para no repetirlas en partidas siguientes hasta que se acaben.

## Añadir preguntas

Cada pregunta en `preguntas.js` es una línea: `["Categoría", "Pregunta", respuesta, "Explicación", dificultad]`. La respuesta tiene que ser un número entero del 0 al 10, y la dificultad 1 (fácil), 2 (media) o 3 (difícil). Si un dato puede cambiar con el tiempo, pon el año en la pregunta ("hasta 2025…").
