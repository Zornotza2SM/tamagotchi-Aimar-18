Hemen duzu euskarara itzulita, kodea, formatua eta irudien erreferentziak mantenduz:

# 👾 PROIEKTUA: PIXEL MASKOTA (Tamagotchi JS)

<img src="image.png" alt="alt text" width="100">
<img src="image-1.png" alt="alt text" width="400">
<img src="image.png" alt="alt text" width="100">

  - [👾 PROIEKTUA: PIXEL MASKOTA (Tamagotchi JS)](https://www.google.com/search?q=%23-proiektua-pixel-maskota-tamagotchi-js)
      - [🛠️ 0. FASEA: Eskeletoa (HTML eta CSS)](https://www.google.com/search?q=%23%EF%B8%8F-0-fasea-eskeletoa-html-eta-css)
      - [🧠 1. FASEA: Modeloa (Datuak)](https://www.google.com/search?q=%23-1-fasea-modeloa-datuak)
      - [👁️ 2. FASEA: Bista (Errenderizatzea)](https://www.google.com/search?q=%23%EF%B8%8F-2-fasea-bista-errenderizatzea)
      - [🎮 3. FASEA: Eguneratzea (Interakzioa)](https://www.google.com/search?q=%23-3-fasea-eguneratzea-interakzioa)
      - [⏳ 4. FASEA: Denboraren Igarotzea (Automatikoa)](https://www.google.com/search?q=%23-4-fasea-denboraren-igarotzea-automatikoa)
      - [💀 5. FASEA: Baldintzazko Errenderizatzea (Game Over)](https://www.google.com/search?q=%23-5-fasea-baldintzazko-errenderizatzea-game-over)
  - [🚀 2. MAILA: Animazioak eta Mekanika Aurreratuak](https://www.google.com/search?q=%23-2-maila-animazioak-eta-mekanika-aurreratuak)
      - [🎨 6. FASEA: Botoiak Estilizatzen (CSS Pro)](https://www.google.com/search?q=%23-6-fasea-botoiak-estilizatzen-css-pro)
      - [🎬 7. FASEA: Lottie Integratzen (Animazioak)](https://www.google.com/search?q=%23-7-fasea-lottie-integratzen-animazioak)
      - [⏱️ 8. FASEA: Itxaronaldiak/Cooldowns (Joko Mekanika)](https://www.google.com/search?q=%23%EF%B8%8F-8-fasea-itxaronaldiakcooldowns-joko-mekanika)
          - [🧩 Azken Kodearen Laburpena (Egitura Mentala)](https://www.google.com/search?q=%23-azken-kodearen-laburpena-egitura-mentala)

**Helburua:** "Beharrak" (gosea eta zoriontasuna) dituen maskota birtual bat sortzea. Denborak aurrera egin ahala, gose handiagoa izango du eta tristeago egongo da, eta zuk botoiak sakatu beharko dituzu zaintzeko.
**Arkitektura:** Modeloa - Bista - Eguneratzea (MVU).

-----

## 🛠️ 0. FASEA: Eskeletoa (HTML eta CSS)

Diseinatzen denbora galdu ez dezazun, hemen duzu oinarrizko egitura. Kopiatu hau zure fitxategian.

**HTML:**

```html
<div id="app"></div>
```

**CSS (Gehitu zure estilo-orrian):**

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

## 🧠 1. FASEA: Modeloa (Datuak)

Kontagailuaren adibidean `let modeloa = 7` zenuen bezala, hemen gure maskotaren egoera definitzeko aldagaiak behar ditugu.

**Zure misioa:**
Definitu bi aldagai global zure script-aren hasieran:

1.  `hambre` (gosea): `0`n hasten da (0 beteta da, 10 gosez hilda).
2.  `felicidad` (zoriontasuna): `10`ean hasten da (10 oso pozik da, 0 deprimituta).

<!-- end list -->

```javascript
// --- MODELOA ---
let hambre = 0;
let felicidad = 10;
```

-----

## 👁️ 2. FASEA: Bista (Errenderizatzea)

Orain `vista()` funtzioa sortuko dugu. Funtzio honek HTMLa margotu behar du ereduko datuetan oinarrituta.

**Zure misioa:**
Kopiatu eta osatu funtzioa. Fijatu `________` hutsuneetan.

```javascript
// --- BISTA ---
function vista() {
    // 1. HTMLa sortzen dugu
    document.getElementById("app").innerHTML = `
        <div class="pet-screen">
            <h1>PIXEL PET</h1>
            
            <div class="pet-face">
                👾 
            </div>

            <div class="stats">
                <div>🍗 Gosea: ${________}</div>
                <div>❤️ Zoriontasuna: ${________}</div>
            </div>

            <div class="controls">
                <button class="boton" id="btn-comer">Jana eman</button>
                <button class="boton" id="btn-jugar">Jolastu</button>
            </div>
        </div>
    `;

    // HEMEN JOANGO DIRA GERTAERAK (3. FASEA)
}

// Bista lehen aldiz deitzen dugu zerbait ager dadin
vista();
```

> **✅ PROBA:** Gorde eta ireki nabigatzailea. Maskota eta 0 eta 10 zenbakiak ikusi beharkozenituzke. Zenbakiak ikusten ez badituzu, berrikusi aldagaiak.

:octocat: Igo aldaketak biltegira mezu honekin: "1. Maila osatuta: Modeloa eta Bista".

-----

## 🎮 3. FASEA: Eguneratzea (Interakzioa)

Kontagailuan bezala, `onclick` gertaerek `vista` funtzioaren **barruan** joan behar dute, HTMLa sortu eta berehala.

**Jokoaren logika:**

  * **Jana eman:** Gosea puntu 1 jaisten da (`hambre--`).
  * **Jolastu:** Zoriontasuna puntu 1 igotzen da (`felicidad++`).

**Zure misioa:**
Gehitu kode hau `vista()` funtzioaren barruan, "HEMEN JOANGO DIRA GERTAERAK" dioen tokian.

```javascript
    // --- EGUNERATZEA (Gertaerak) ---
    
    document.getElementById("btn-comer").onclick = () => {
        // Logika: Gosea 0 baino handiagoa bada, 1 kentzen dugu.
        if (hambre > 0) {
            hambre--; 
        }
        vista(); // GARRANTZITSUA: Berriro margotzen dugu
    }

    document.getElementById("btn-jugar").onclick = () => {
        // Logika: Zoriontasuna 10 baino txikiagoa bada, 1 gehitzen dugu.
        if (felicidad < 10) {
            ________++; // Osatu hau
        }
        vista(); // Bista birkargatzen dugu
    }
```

> **✅ PROBA:** Egin klik botoietan. Zenbakiak aldatzen dira? Hala bada, MVU arkitektura funtzionatzen ari da.

:octocat: Igo aldaketak biltegira mezu honekin: "1. Maila osatuta: Modeloa, Bista eta Eguneratzea".

-----

## ⏳ 4. FASEA: Denboraren Igarotzea (Automatikoa)

Semaforoaren adibidean `setTimeout` bista barruan erabili zenuen. Hemen, bista birkargatzen duten botoiak ere baditugunez, `setTimeout` barruan jartzen badugu, tenporizadoreak bikoiztu egingo dira klik egiten duzun bakoitzean\!

Akatsak saihesteko, `pasoDelTiempo()` izeneko funtzio bereizi bat egingo dugu.

**Zure misioa:**
Kopiatu funtzio hau bistatik **kanpo** (zure fitxategiaren amaieran) eta exekutatu.

```javascript
// --- DENBORA BEGIZTA (LOOP) ---

function pasoDelTiempo() {
    // 2 segundoro (2000ms), maskotak okerrera egiten du
    setTimeout(() => {
        
        // 1. Estatistikak okertzen ditugu
        hambre++;      // Gosea sartzen zaio
        felicidad--;   // Tristetu egiten da

        // 2. Balioak mugatzen ditugu (infinituak izan ez daitezen)
        if (hambre > 10) hambre = 10;
        if (felicidad < 0) felicidad = 0;

        // 3. Pantaila eguneratzen dugu
        vista();

        // 4. Tenporizadoreari berriro deitzen diogu (Begizta infinitua)
        pasoDelTiempo();

    }, 2000);
}

// DENBORA HASI
pasoDelTiempo();
```

> **✅ PROBA:** Ez ukitu ezer. Itxaron segundo batzuk. Gosea igo eta zoriontasuna jaisten al da bakarrik? Zure maskota bizirik dago\!

:octocat: Igo aldaketak biltegira mezu honekin: "1. Maila osatuta: Denbora Begizta".

-----

## 💀 5. FASEA: Baldintzazko Errenderizatzea (Game Over)

Orain **operadore hirutarra** (ternarioa) erabiliko dugu (semaforoan erabili zenuena: `baldintza ? egia : gezurra`) maskotaren aurpegia aldatzeko.

**Zure misioa:**
`vista()` funtzioa aldatuko dugu. `👾` aurpegia margotzen dugun lerroa aldatu behar duzu.

1.  Bilatu `<div class="pet-face"> 👾 </div>` lerroa.
2.  Ordezkatu logika argi batekin:
      * `hambre` 10era iristen bada edo `felicidad` 0ra iristen bada... maskota hil egiten da 💀.
      * Bestela, bizirik jarraitzen du 👾.

Aldatu zure HTMLa JS barruan honela:

```javascript
    // Lehenik bizirik edo hilda dagoen kalkulatzen dugu
    let estaMuerto = (hambre >= 10 || felicidad <= 0);

    // Aurpegirako aldagai bat sortzen dugu
    // estaMuerto true bada -> garezurra. false bada -> estralurtarra.
    let cara = estaMuerto ? "💀" : "👾";
    
    // AUKERAKOA: Joko amaierako mezua
    let mensaje = estaMuerto ? "<div class='game-over'>GAME OVER</div>" : "";

    document.getElementById("app").innerHTML = `
        <div class="pet-screen">
            <h1>PIXEL PET</h1>
            
            <div class="pet-face">
                ${cara}
            </div>
            
            ${mensaje}

            <div class="stats">
             ... (zure kodearen gainerakoa berdin jarraitzen du)
```

**⚠️ Erronka Extra:**
Maskota hilda badago (`estaMuerto == true`), jateko eta jolasteko botoiek ez lukete funtzionatu behar. Bildu botoien `onclick` logika `if (!estaMuerto) { ... }` baten barruan.

:octocat: Igo aldaketak biltegira mezu honekin: "1. Maila osatuta: Game Over eta Baldintzak".

-----

# 🚀 2. MAILA: Animazioak eta Mekanika Aurreratuak

**Helburua:** Erantzun bisuala hobetzea Lottie animazioak erabiliz (fitxategirik deskargatu gabe, soilik web bidez) eta "Cooldowns" (itxaronaldiak) gehitzea jokoa desafiagarriagoa izan dadin.

-----

## 🎨 6. FASEA: Botoiak Estilizatzen (CSS Pro)

Oinarrizko botoi horiak aspergarriak dira. "Gamer" estilo bat emango diegu eta itxura bisual bat prestatu desaktibatuta daudenerako (Cooldown).

**Zure misioa:**
Ordezkatu edo eguneratu `.boton` klasea zure CSSan eta gehitu `.boton:disabled`.

```css
/* Botoi normala 3D efektuarekin */
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
    box-shadow: 0px 4px 0px #c7861b; /* "Itzalak" egiten du 3D efektua */
    transition: all 0.1s;
}

/* Sakatzean efektua */
.boton:active {
    position: relative;
    top: 4px; /* Beherantz mugitzen da */
    box-shadow: 0px 0px 0px #c7861b; /* Itzala desagertzen da */
}

/* Botoia DESAKTIBATUTA (Cooldown-ean dagoenean) */
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

## 🎬 7. FASEA: Lottie Integratzen (Animazioak)

Ikono estatikoen ordez (🍗 ❤️), mugitzen diren animazioak jarriko ditugu. **LottieFiles** liburutegia erabiliko dugu.

**7.1 Urratsa: Liburutegia inportatu**
Honek funtziona dezan, script hau gehitu behar duzu zure HTMLan, `</body>` etiketa itxi baino lehen edo `<head>` barruan:

```html
<script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
```

**7.2 Urratsa: Bista Eguneratu**
`vista()` funtzioaren barruko `stats` atala aldatuko dugu.
Emojiak `<lottie-player>` etiketekin ordezkatuko ditugu.

**Zure misioa:**
Bilatu `div class="stats"` hori `vista()` barruan eta aldatu honegatik. Fijatu nola erabiltzen ditugun operadore hirutarrak animazioa egoeraren arabera aldatzeko.

```javascript
    // Logika bisuala:
    // Zoriontasuna baxua bada (< 4), bihotz hautsia jartzen dugu. Bestela, taupaka ari dena.
    let urlCorazon = felicidad < 4 
        ? "https://assets9.lottiefiles.com/private_files/lf30_434185.json" // Bihotz hautsia
        : "https://assets10.lottiefiles.com/packages/lf20_7z8wtyb0.json"; // Bihotz taupakaria

    // HTML bista barruan:
    // ... return edo innerHTML barruan ...
    <div class="stats">
        <div style="display:flex; align-items:center; flex-direction:column">
            <lottie-player src="https://assets10.lottiefiles.com/packages/lf20_j1adxa sv.json"  background="transparent"  speed="1"  style="width: 50px; height: 50px;" loop autoplay></lottie-player>
            <span>Gosea: ${hambre}</span>
        </div>

        <div style="display:flex; align-items:center; flex-direction:column">
            <lottie-player src="${urlCorazon}"  background="transparent"  speed="1"  style="width: 50px; height: 50px;" loop autoplay></lottie-player>
            <span>Zoriontasuna: ${felicidad}</span>
        </div>
    </div>
```

> **✅ PROBA:** Birkargatu orria. Hanburgesa bat biraka eta bihotz bat taupaka ikusi beharko zenituzke. Zoriontasuna 4tik jaisten bada, bihotza hautsi beharko litzateke.

-----

:octocat: Igo aldaketak biltegira mezu honekin: "2. Maila 1. zatia osatuta: Lottie eta Estiloak".

## ⏱️ 8. FASEA: Itxaronaldiak/Cooldowns (Joko Mekanika)

Orain erabiltzaileak segundoko 50 aldiz "Jana eman" sakatzea saihestuko dugu. Itxaronaldi denbora bat (cooldown) gehituko dugu.

**8.1 Urratsa: Modeloa Eguneratu**
Botoia blokeatuta edo eskuragarri dagoen jakin behar dugu. Gehitu aldagai hauek zure modelora (JS fitxategiaren hasieran).

```javascript
// --- MODELOA ---
// (Aurreko aldagaiak...)
let comiendo = false; // Jaten lanpetuta?
let jugando = false;  // Jolasten lanpetuta?
```

**8.2 Urratsa: Bista Blokeatu**
HTMLari esan behar diogu `comiendo` aldagaia `true` bada, botoiak desgaituta egon behar duela.

Joan botoien atalera zure `vista()` funtzioan eta gehitu `disabled` atributua:

```javascript
    // vista() barruko template string-ean:
    <div class="controls">
        <button class="boton" id="btn-comer" ${ comiendo ? "disabled" : "" }>
            ${ comiendo ? "Murtxikatzen..." : "Jana eman" }
        </button>

        <button class="boton" id="btn-jugar" ${ jugando ? "disabled" : "" }>
            ${ jugando ? "Nekatuta..." : "Jolastu" }
        </button>
    </div>
```

:octocat: Igo aldaketak biltegira mezu honekin: "2. Maila 1. zatia osatuta: Lottie eta Estiloak".

**8.3 Urratsa: Cooldown-aren Logika (Update)**
Orain `onclick` gertaera aldatuko dugu. Sakatzen dugunean:

1.  Egoera "lanpetuta"ra aldatzen dugu.
2.  Bista eguneratzen dugu (botoia gris jarriko da).
3.  1 edo 2 segundo itxaroten dugu.
4.  Egoera "libre"ra aldatzen dugu.
5.  Bista eguneratzen dugu berriro (botoia horira itzultzen da).

Ordezkatu jateko zure `onclick` gertaera honekin:

```javascript
    document.getElementById("btn-comer").onclick = () => {
        if (hambre > 0) {
            hambre--;
            
            // 1. Botoia blokeatzen dugu
            comiendo = true;
            vista(); // Botoi grisa margotzen dugu ("Murtxikatzen...")

            // 2. Segundo 1eko (1000ms) tenporizadorea hasten dugu
            setTimeout(() => {
                comiendo = false; // Desblokeatzen dugu
                vista(); // Botoi horia margotzen dugu berriro
            }, 1000);
        }
    }
```

**Zure misioa:**
Egin zuk zeuk **"Jolastu"** botoiaren logika.

  * `jugando` aldagaia erabili behar du.
  * Egin cooldown-a luzeagoa izan dadin (adib. 2000ms), jolasteak gehiago nekatzen duelako.

:octocat: Igo aldaketak biltegira mezu honekin: "2. Maila osatuta: Animazioak eta Cooldown-ak".

-----

### 🧩 Azken Kodearen Laburpena (Egitura Mentala)

Ulertu duzula egiaztatzeko, zure kodeak fluxu hau jarraitu beharko luke:

1.  **Modeloa:** `hambre`, `felicidad`, `comiendo`, `jugando`.
2.  **Bista:**
      * Lottie URL-a kalkulatzen du zoriontasunaren arabera.
      * Lottie Player-ak margotzen ditu.
      * Botoiak margotzen ditu `disabled` atributuarekin `comiendo/jugando` true bada.
      * `onclick` gertaerak esleitzen ditu.
3.  **Gertaerak (Update):**
      * Modeloa aldatzen du (`hambre--`, `comiendo = true`).
      * `vista()` deitzen du.
      * `setTimeout` jaurtitzen du -\> (`comiendo = false`, `vista()`).
4.  **Begizta:** `pasoDelTiempo()` atzeko planoan exekutatzen da bizitza kenduz.

> **🏆 AZKEN EMAITZA:**
> Orain joko bat daukazu non ez den nahikoa azkar klik egitea. Botoien itxaronaldiak kudeatu behar dituzu zure maskotari bizitza kentzen dion denboraren aurka borrokatzen duzun bitartean. Hori bai dela benetako jokoa\!