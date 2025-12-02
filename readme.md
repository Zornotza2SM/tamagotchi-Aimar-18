[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/PHpjbIZR)

# 👾 PROYECTO: MASCOTA PIXEL (Tamagotchi JS)

<img src="image.png" alt="alt text" width="100"/> 
<img src="image-1.png" alt="alt text" width="400"/>
<img src="image.png" alt="alt text" width="100"/> 

- [👾 PROYECTO: MASCOTA PIXEL (Tamagotchi JS)](#-proyecto-mascota-pixel-tamagotchi-js)
  - [🛠️ FASE 0: El Esqueleto (HTML y CSS)](#️-fase-0-el-esqueleto-html-y-css)
  - [🧠 FASE 1: El Modelo (Datos)](#-fase-1-el-modelo-datos)
  - [👁️ FASE 2: La Vista (Renderizado)](#️-fase-2-la-vista-renderizado)
  - [🎮 FASE 3: Actualización (Interacción)](#-fase-3-actualización-interacción)
  - [⏳ FASE 4: El Paso del Tiempo (Automático)](#-fase-4-el-paso-del-tiempo-automático)
  - [💀 FASE 5: Renderizado Condicional (Game Over)](#-fase-5-renderizado-condicional-game-over)
- [🚀 NIVEL 2: Animaciones y Mecánicas Avanzadas](#-nivel-2-animaciones-y-mecánicas-avanzadas)
  - [🎨 FASE 6: Estilizando los Botones (CSS Pro)](#-fase-6-estilizando-los-botones-css-pro)
  - [🎬 FASE 7: Integrando Lottie (Animaciones)](#-fase-7-integrando-lottie-animaciones)
  - [⏱️ FASE 8: Cooldowns (Mecánica de Juego)](#️-fase-8-cooldowns-mecánica-de-juego)
    - [🧩 Resumen del Código Final (Estructura Mental)](#-resumen-del-código-final-estructura-mental)


**Objetivo:** Crear una mascota virtual que tiene "necesidades" (hambre y felicidad). El tiempo hará que tenga más hambre y esté más triste, y tú tendrás que pulsar botones para cuidarla.
**Arquitectura:** Modelo - Vista - Actualización.

-----

## 🛠️ FASE 0: El Esqueleto (HTML y CSS)

Para que no pierdas tiempo diseñando, aquí tienes la estructura base. Copia esto en tu archivo.

**HTML:**

```html
<div id="app"></div>
```

**CSS (Añádelo a tu hoja de estilos):**

```css
body {
    font-family: 'Courier New', Courier, monospace;
    background-color: #222;
    color: white;
    text-align: center;
}

.pet-screen {
    border: 4px solid #fff;
    width: 300px;
    margin: 0 auto;
    padding: 20px;
    border-radius: 10px;
    background-color: #444;
}

.pet-face {
    font-size: 80px;
    margin: 20px 0;
}

.stats {
    display: flex;
    justify-content: space-around;
    font-size: 18px;
    margin-bottom: 20px;
}

.boton {
    background-color: #f5c103;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    font-weight: bold;
    margin: 5px;
}

.boton:hover { background-color: #fff; }
.game-over { color: red; font-size: 30px; font-weight: bold; }
```

-----

## 🧠 FASE 1: El Modelo (Datos)

Igual que en el ejemplo del contador tenías `let modeloa = 7`, aquí necesitamos variables para definir el estado de nuestra mascota.

**Tu misión:**
Define dos variables globales al inicio de tu script:

1.  `hambre`: Empieza en `0` (0 es lleno, 10 es muerto de hambre).
2.  `felicidad`: Empieza en `10` (10 es muy feliz, 0 es deprimido).

<!-- end list -->

```javascript
// --- MODELO ---
let hambre = 0;
let felicidad = 10;
```

-----

## 👁️ FASE 2: La Vista (Renderizado)

Ahora vamos a crear la función `vista()`. Esta función debe pintar el HTML basándose en los datos del modelo.

**Tu misión:**
Copia y completa la función. Fíjate en los huecos `________`.

```javascript
// --- VISTA ---
function vista() {
    // 1. Generamos el HTML
    document.getElementById("app").innerHTML = `
        <div class="pet-screen">
            <h1>PIXEL PET</h1>
            
            <div class="pet-face">
                👾 
            </div>

            <div class="stats">
                <div>🍗 Hambre: ${________}</div>
                <div>❤️ Felicidad: ${________}</div>
            </div>

            <div class="controls">
                <button class="boton" id="btn-comer">Dar Comida</button>
                <button class="boton" id="btn-jugar">Jugar</button>
            </div>
        </div>
    `;

    // AQUI IRÁN LOS EVENTOS (FASE 3)
}

// Llamamos a la vista por primera vez para que aparezca algo
vista();
```

> **✅ PRUEBA:** Guarda y abre el navegador. Deberías ver a la mascota y los números 0 y 10. Si no ves los números, revisa las variables.

:octocat: Sube los cambios al repositorio con el mensaje "Nivel 1 completado: Modelo y Vista".

-----

## 🎮 FASE 3: Actualización (Interacción)

Igual que en el contador, los eventos `onclick` deben ir **dentro** de la función `vista`, justo después de crear el HTML.

**Lógica del juego:**

  * **Dar Comida:** El hambre baja 1 punto (`hambre--`).
  * **Jugar:** La felicidad sube 1 punto (`felicidad++`).

**Tu misión:**
Añade este código dentro de la función `vista()`, donde dice "AQUI IRÁN LOS EVENTOS".

```javascript
    // --- ACTUALIZACIÓN (Eventos) ---
    
    document.getElementById("btn-comer").onclick = () => {
        // Lógica: Si el hambre es mayor que 0, restamos 1.
        if (hambre > 0) {
            hambre--; 
        }
        vista(); // IMPORTANTE: Volvemos a pintar
    }

    document.getElementById("btn-jugar").onclick = () => {
        // Lógica: Si felicidad es menor que 10, sumamos 1.
        if (felicidad < 10) {
            ________++; // Completa esto
        }
        vista(); // Recargamos la vista
    }
```

> **✅ PRUEBA:** Haz click en los botones. ¿Cambian los números? Si es así, la arquitectura MVU está funcionando.

:octocat: Sube los cambios al repositorio con el mensaje "Nivel 1 completado: Modelo, Vista y Actualización".

-----

## ⏳ FASE 4: El Paso del Tiempo (Automático)

En el ejemplo del semáforo usaste `setTimeout` dentro de la vista. Aquí, como tenemos botones que también recargan la vista, si ponemos el `setTimeout` dentro, ¡se duplicarán los temporizadores cada vez que hagas click\!

Para evitar errores, haremos una función separada llamada `pasoDelTiempo()`.

**Tu misión:**
Copia esta función **fuera** de la vista (al final de tu archivo) y ejecútala.

```javascript
// --- LOOP DEL TIEMPO ---

function pasoDelTiempo() {
    // Cada 2 segundos (2000ms), la mascota empeora
    setTimeout(() => {
        
        // 1. Empeoramos las estadísticas
        hambre++;      // Le entra hambre
        felicidad--;   // Se pone triste

        // 2. Limitamos los valores (para que no sean infinitos)
        if (hambre > 10) hambre = 10;
        if (felicidad < 0) felicidad = 0;

        // 3. Actualizamos la pantalla
        vista();

        // 4. Volvemos a llamar al temporizador (Bucle infinito)
        pasoDelTiempo();

    }, 2000);
}

// INICIAR EL TIEMPO
pasoDelTiempo();
```

> **✅ PRUEBA:** No toques nada. Espera unos segundos. ¿Sube el hambre y baja la felicidad sola? ¡Tu mascota está viva\!
>

:octocat: Sube los cambios al repositorio con el mensaje "Nivel 1 completado: Loop del Tiempo".

-----

## 💀 FASE 5: Renderizado Condicional (Game Over)

Ahora usaremos el **operador ternario** (el que usaste en el semáforo: `condición ? verdadero : falso`) para cambiar la cara de la mascota.

**Tu misión:**
Vamos a modificar la función `vista()`. Tienes que cambiar la línea donde pintamos la cara `👾`.

1.  Busca la línea `<div class="pet-face"> 👾 </div>`.
2.  Sustitúyela por una lógica inteligente:
      * Si `hambre` llega a 10 o `felicidad` llega a 0... la mascota muere 💀.
      * Si no, sigue viva 👾.

Modifica tu HTML dentro de JS así:

```javascript
    // Primero calculamos si está vivo o muerto
    let estaMuerto = (hambre >= 10 || felicidad <= 0);

    // Creamos una variable para la cara
    // Si estaMuerto es true -> calavera. Si es false -> alien.
    let cara = estaMuerto ? "💀" : "👾";
    
    // OPCIONAL: Mensaje de fin de juego
    let mensaje = estaMuerto ? "<div class='game-over'>GAME OVER</div>" : "";

    document.getElementById("app").innerHTML = `
        <div class="pet-screen">
            <h1>PIXEL PET</h1>
            
            <div class="pet-face">
                ${cara}
            </div>
            
            ${mensaje}

            <div class="stats">
             ... (el resto de tu código sigue igual)
```

**⚠️ Reto Extra:**
Si la mascota está muerta (`estaMuerto == true`), los botones de comer y jugar no deberían funcionar. Envuelve la lógica de los botones `onclick` en un `if (!estaMuerto) { ... }`.


:octocat: Sube los cambios al repositorio con el mensaje "Nivel 1 completado: Game Over y Condicionales".

-----

# 🚀 NIVEL 2: Animaciones y Mecánicas Avanzadas

**Objetivo:** Mejorar la respuesta visual usando animaciones Lottie (sin descargar archivos, solo vía web) y añadir "Cooldowns" (tiempos de espera) para que el juego sea más desafiante.

-----

## 🎨 FASE 6: Estilizando los Botones (CSS Pro)

Los botones amarillos básicos son aburridos. Vamos a darles un estilo "Gamer" y preparar un estilo visual para cuando estén desactivados (Cooldown).

**Tu misión:**
Sustituye o actualiza la clase `.boton` en tu CSS y añade `.boton:disabled`.

```css
/* Botón normal con efecto 3D */
.boton {
    background: linear-gradient(to bottom, #ffec64 5%, #ffab23 100%);
    background-color: #ffec64;
    border-radius: 6px;
    border: 1px solid #ffaa22;
    display: inline-block;
    cursor: pointer;
    color: #333;
    font-family: Arial;
    font-size: 15px;
    font-weight: bold;
    padding: 10px 24px;
    text-decoration: none;
    text-shadow: 0px 1px 0px #ffee66;
    box-shadow: 0px 4px 0px #c7861b; /* La "sombra" hace el efecto 3D */
    transition: all 0.1s;
}

/* Efecto al pulsar */
.boton:active {
    position: relative;
    top: 4px; /* Se mueve hacia abajo */
    box-shadow: 0px 0px 0px #c7861b; /* Desaparece la sombra */
}

/* Botón DESACTIVADO (Cuando está en cooldown) */
.boton:disabled {
    background: #cccccc;
    border: 1px solid #999999;
    color: #666666;
    cursor: not-allowed;
    box-shadow: none;
    top: 0px;
    filter: grayscale(100%);
}
```

-----

## 🎬 FASE 7: Integrando Lottie (Animaciones)

En lugar de iconos estáticos (🍗 ❤️), vamos a poner animaciones que se muevan. Usaremos la librería **LottieFiles**.

**Paso 7.1: Importar la librería**
Para que esto funcione, debes añadir este script en tu HTML, justo antes de cerrar la etiqueta `</body>` o en el `<head>`:

```html
<script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
```

**Paso 7.2: Actualizar la Vista**
Vamos a cambiar la sección de `stats` dentro de tu función `vista()`.
Sustituiremos los emojis por etiquetas `<lottie-player>`.

**Tu misión:**
Busca el `div class="stats"` dentro de `vista()` y cámbialo por este. Fíjate cómo usamos operadores ternarios para cambiar la animación según el estado.

```javascript
    // Lógica visual:
    // Si la felicidad es baja (< 4), ponemos un corazón roto. Si no, uno latiendo.
    let urlCorazon = felicidad < 4 
        ? "https://assets9.lottiefiles.com/private_files/lf30_434185.json" // Corazón roto
        : "https://assets10.lottiefiles.com/packages/lf20_7z8wtyb0.json"; // Corazón latiendo

    // HTML dentro de la vista:
    // ... dentro del return o innerHTML ...
    <div class="stats">
        <div style="display:flex; align-items:center; flex-direction:column">
            <lottie-player src="https://assets10.lottiefiles.com/packages/lf20_j1adxa sv.json"  background="transparent"  speed="1"  style="width: 50px; height: 50px;" loop autoplay></lottie-player>
            <span>Hambre: ${hambre}</span>
        </div>

        <div style="display:flex; align-items:center; flex-direction:column">
            <lottie-player src="${urlCorazon}"  background="transparent"  speed="1"  style="width: 50px; height: 50px;" loop autoplay></lottie-player>
            <span>Felicidad: ${felicidad}</span>
        </div>
    </div>
```

> **✅ PRUEBA:** Recarga la página. Deberías ver una hamburguesa girando y un corazón latiendo. Si la felicidad baja de 4, el corazón debería romperse.

-----

:octocat: Sube los cambios al repositorio con el mensaje "Nivel 2 parte 1 completada: Lottie y Estilos".

## ⏱️ FASE 8: Cooldowns (Mecánica de Juego)

Ahora evitaremos que el usuario pulse "Comer" 50 veces por segundo. Vamos a añadir un tiempo de espera (cooldown).

**Paso 8.1: Actualizar el Modelo**
Necesitamos saber si el botón está bloqueado o disponible. Añade estas variables a tu modelo (al principio del archivo JS).

```javascript
// --- MODELO ---
// (Variables anteriores...)
let comiendo = false; // ¿Está ocupado comiendo?
let jugando = false;  // ¿Está ocupado jugando?
```

**Paso 8.2: Bloquear la Vista**
Tenemos que decirle al HTML que si la variable `comiendo` es `true`, el botón debe estar deshabilitado.

Ve a la sección de los botones en tu función `vista()` y añade el atributo `disabled`:

```javascript
    // Dentro del template string en vista():
    <div class="controls">
        <button class="boton" id="btn-comer" ${ comiendo ? "disabled" : "" }>
            ${ comiendo ? "Masticando..." : "Dar Comida" }
        </button>

        <button class="boton" id="btn-jugar" ${ jugando ? "disabled" : "" }>
            ${ jugando ? "Cansado..." : "Jugar" }
        </button>
    </div>
```

:octocat: Sube los cambios al repositorio con el mensaje "Nivel 2 parte 1 completada: Lottie y Estilos".

**Paso 8.3: La Lógica del Cooldown (Update)**
Ahora modificamos el evento `onclick`. Cuando pulsamos:

1.  Cambiamos el estado a "ocupado".
2.  Actualizamos la vista (el botón se pondrá gris).
3.  Esperamos 1 o 2 segundos.
4.  Cambiamos el estado a "libre".
5.  Actualizamos la vista otra vez (el botón vuelve a amarillo).

Sustituye tu evento `onclick` de comer por este:

```javascript
    document.getElementById("btn-comer").onclick = () => {
        if (hambre > 0) {
            hambre--;
            
            // 1. Bloqueamos el botón
            comiendo = true;
            vista(); // Pintamos el botón gris ("Masticando...")

            // 2. Iniciamos el temporizador de 1 segundo (1000ms)
            setTimeout(() => {
                comiendo = false; // Desbloqueamos
                vista(); // Pintamos el botón amarillo otra vez
            }, 1000);
        }
    }
```

**Tu misión:**
Haz tú mismo la lógica para el botón de **"Jugar"**.

  * Debe usar la variable `jugando`.
  * Haz que el cooldown sea más largo (ej. 2000ms) porque jugar cansa más.

:octocat: Sube los cambios al repositorio con el mensaje "Nivel 2 completado: Animaciones y Cooldowns".

-----

### 🧩 Resumen del Código Final (Estructura Mental)

Para comprobar que lo has entendido, tu código debería seguir este flujo:

1.  **Modelo:** `hambre`, `felicidad`, `comiendo`, `jugando`.
2.  **Vista:**
      * Calcula URL del Lottie según felicidad.
      * Pinta Lottie Players.
      * Pinta botones con atributo `disabled` si `comiendo/jugando` es true.
      * Asigna eventos `onclick`.
3.  **Eventos (Update):**
      * Cambia modelo (`hambre--`, `comiendo = true`).
      * Llama a `vista()`.
      * Lanza `setTimeout` -\> (`comiendo = false`, `vista()`).
4.  **Loop:** `pasoDelTiempo()` sigue corriendo de fondo restando vida.

> **🏆 RESULTADO FINAL:**
> Ahora tienes un juego donde no basta con clickear rápido. Tienes que gestionar los tiempos de espera de los botones mientras luchas contra el tiempo que le quita vida a tu mascota. ¡Eso es un juego real\!


