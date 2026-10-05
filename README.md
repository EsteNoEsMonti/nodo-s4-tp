# Trabajo Práctico - Sprint 4: Consumiendo una API

---

## 📌 Antes de arrancar

Este TP es distinto a los anteriores. **No vas a encontrar un paso a paso.**

Hasta acá te di la consigna masticada: los bloques por clase, la estructura de carpetas dibujada, las recetas para copiar. Se terminó. Este sprint arranca con lo que de verdad vas a recibir en un trabajo: **una idea de producto y una fecha.** El cómo es tuyo.

> 🎯 **La regla madre, y la única que importa:** está habilitado **todo lo que vimos en la cursada** — estado, efectos, custom hooks, contexto, formularios, persistencia, y ahora peticiones a APIs. No hay lista de "lo que va y lo que no va". Si lo vimos, es tuyo para usar. Elegís vos qué corresponde.

### 🧑‍💻 Y esto es lo que cambia de verdad: cómo se evalúa

A partir de este TP **te evalúo como si fueras parte de un equipo de desarrollo**, no como a un alumno siguiendo una guía. Eso significa:

- **El pedido es el qué, no el cómo.** Nadie en un laburo te va a decir "creá un componente `Card.jsx` y pasale estas props". Te dicen "que el usuario pueda buscar y guardar favoritos". El resto lo resolvés y lo justificás.
- **Las decisiones son tuyas y las vas a defender.** Qué estructura de carpetas, `fetch` o `axios`, dónde vive cada estado, qué poné en un contexto y qué no. No hay una respuesta correcta única: hay decisiones que podés explicar y decisiones que no.
- **Lo que no sabés explicar, no cuenta.** Si hay código en tu entrega que no podés justificar línea por línea, es como si no estuviera. Un TP más chico y entendido vale más que uno grande lleno de cosas que te tiró la IA.

---

## 🎯 El pedido

Construí una app en **React** que **consuma una API pública**, muestre los resultados, permita **buscar** y permita **guardar favoritos que sobrevivan a la recarga**.

Eso es todo el pedido. Como en el laburo.

Las decisiones de producto que quedan en tus manos:
- Qué API usás (que tenga búsqueda por texto y datos lindos para armar una card).
- Cómo mostrás los favoritos (modal, panel, otra vista — lo que tenga sentido).
- Cómo se ve. Que parezca un producto, no un ejercicio.

### 🌐 APIs sugeridas

Elegí una que te guste y que tenga **búsqueda por texto** y **datos lindos por item** (una imagen y dos o tres campos, mínimo). Probala en Postman antes de comprometerte: si la búsqueda no anda como esperás, mejor enterarte ahora.

| API | Para qué sirve |
|---|---|
| ⭐ **[Rick and Morty](https://rickandmortyapi.com/documentation)** | **La recomendada.** Búsqueda lista para usar, buena imagen por personaje y filtros que dan mucho juego. Es la que vamos a usar en el ejercicio en vivo |
| [PokeAPI](https://pokeapi.co/docs/v2) | Clásica, un montón de data por item |
| [TheMealDB](https://www.themealdb.com/api.php) | Recetas, con imagen linda |
| [Jikan (anime)](https://docs.api.jikan.moe/) | Si te gusta el anime |
| [OpenWeather](https://openweathermap.org/api) | Clima. **Requiere API key** → te sirve para practicar lo de `.env` |

> ⭐ Si no sabés cuál elegir, andá con **Rick and Morty**. Es la que vamos a trabajar en clase y la que mejor te va a acompañar en la Review.

### Lo único no negociable

Porque es lo nuevo del sprint y es lo que vine a enseñar:

- **La data viene de una API de verdad**, no de un array hardcodeado.
- **Se maneja el ciclo completo de una petición:** que el usuario vea cuándo está cargando, que vea un error legible si algo falla, y que nunca quede la pantalla congelada o rota.
- **La búsqueda le pega a la API**, no es un filtro sobre un único lote que trajiste una vez.
- **Los favoritos persisten.** Vuelve mañana y siguen ahí.
- **Nada sensible hardcodeado.** URLs de config y API keys van en variables de entorno (`.env`).

> 🔑 **Sobre el `.env`, y escuchá esto bien porque es del mundo real:** en un proyecto serio el `.env` **nunca** se sube al repo — va en el `.gitignore` siempre, porque ahí viven claves y secretos. **Pero para la cursada vamos a hacer la excepción y sí lo vamos a subir**, por una cuestión práctica: así puedo correr tu proyecto sin pedirte las claves por privado. Es la única concesión. El `node_modules` **ese sí que no se sube jamás**, ni en la cursada ni en la vida.

Todo lo demás —estructura, componentes, estilos, si metés o no un contexto, un custom hook o un formulario— es criterio tuyo.

---

## 🤖 Sobre la IA

Usala. En un equipo real la vas a usar. Pero el pedido viene con una condición de ese mismo mundo real: **sos responsable de lo que entregás.**

Si la IA te mete una librería que no vimos, un hook de optimización que no hace falta, o una solución que no entendés, en la Review va a quedar expuesto en la primera pregunta. No porque esté "prohibido", sino porque **no vas a poder explicarlo**, y en un laburo ese código es tu problema cuando se rompe.

> 🗣️ No te voy a preguntar *si* usaste IA. Te voy a preguntar *por qué* tu código hace lo que hace. Si la respuesta es "no sé, me lo generó", ahí tenés el trabajo que te falta.

---

## 📦 Entrega

⚠️ **El TP se entrega subido a un repositorio.** ⚠️

- **Repo público en GitHub, nuevo**, solo con el proyecto.
- **`.gitignore` con `node_modules`.** El `.env` para esta entrega lo subís (ver la aclaración de arriba), pero el `node_modules` no va nunca.
- **App desplegada** (Netlify o Vercel). El link del deploy y el del repo, por el formulario de la plataforma.
- **Commits que cuenten la historia** del trabajo. No un único commit "final".
- **Un `README.md`** que, como en cualquier proyecto serio, le explique a alguien que lo abre por primera vez:
  - Qué es y el link al demo.
  - Qué API usaste (con link a su documentación).
  - Cómo correrlo y qué variables de entorno necesita (dejá un `.env.example`).
  - Las decisiones que tomaste y por qué: `fetch` o `axios`, qué reusaste de sprints anteriores, qué resolviste con IA y qué corregiste a mano.

---

## 🎯 Cómo se evalúa

No hay checklist de 40 ítems. Hay tres preguntas, las mismas que se haría cualquier líder técnico mirando tu entrega:

### 1. ¿Funciona como un producto?

Lo abro, lo uso sin que me expliques nada, y hago el flujo completo: entro, busco, marco un favorito, recargo con F5 y sigue ahí. Apago el WiFi y recargo: tiene que avisarme con un error claro, no romperse. Lo abro en el celular (375px) y se ve bien. Todo esto **en el deploy**, no solo en tu máquina.

### 2. ¿Está bien construido?

Miro el código como miraría el de un compañero de equipo. No busco una estructura exacta: busco **decisiones coherentes**. Que las peticiones estén bien manejadas (carga, error, el efecto con las dependencias correctas), que no haya estado duplicado pudiendo ser derivado, que reuses lo que ya tenías hecho en vez de reescribirlo, que la config sensible no esté hardcodeada, y que la consola esté limpia. Que si otro tiene que tocar esto mañana, pueda.

### 3. ¿Lo podés defender?

Review 1 a 1, 15 minutos, compartiendo pantalla. Tres cosas:

- **Contame el flujo del dato**, desde que el componente se monta hasta que la card aparece. Dónde vive el estado, dónde la petición, cómo manejás carga y error.
- **Un cambio en vivo.** Te pido algo chico (sumar un dato a la card, mostrar el total de favoritos en algún lado, cambiar un mensaje) y lo hacés ahí.
- **Predecí antes de correr.** Te hago romper algo —sacarle el array de dependencias a un efecto, quitarle el `finally` al `try/catch`— y me decís qué va a pasar **antes** de guardar.

> 🎣 Algunas preguntas tienen truco. **"No sé" es una respuesta válida y no baja nota.** Inventar para zafar, sí.

---

📌 Dudas por la plataforma o en clase. Si algo se rompe, mandá el error completo con la pestaña Network abierta, no "no me funciona". 🌍

✨ ÉXITOS ✨
