# Perfil de ViboLínea en itch.io (kit para copiar y pegar)

Pasos: itch.io → tu avatar → **Upload new project**. Los textos de abajo van campo por campo.
La portada es `cover-630x500.png` (en esta misma carpeta).

---

## 1) Datos básicos

| Campo | Qué poner |
|---|---|
| **Title** | ViboLínea |
| **Project URL** | `viblinea` → quedará en `https://TU_USUARIO.itch.io/viblinea` |
| **Short description or tagline** | Juego de ritmo hecho de líneas que tiemblan: sube tu canción y el nivel nace de ella. |
| **Classification** | Games |
| **Kind of project** | **HTML** (Playable in browser) |
| **Release status** | Released |
| **Pricing** | No payments (gratis) |
| **Genre** | Other (en itch.io "Rhythm" no es género, va como etiqueta) |
| **Tags** (máx. 10; sin géneros ni plataformas) | rhythm, music, vector, retro, minimalist, singleplayer, experimental, cute, 3d, short |
| **Cover image** | `cover-630x500.png` |

## 2) Archivo jugable

- Primera vez, a mano: comprime la carpeta `juego/` de modo que `index.html` quede **en la raíz del .zip**, súbelo en *Uploads* y marca **"This file will be played in the browser"**.
- Después, automático: el workflow `.github/workflows/itch.yml` sube la carpeta `juego/` solo (ver README, "Misión Legendaria").

## 3) Embed options (Frame options)

- **Viewport dimensions:** 960 × 600 (el juego se adapta al tamaño de la ventana)
- **Fullscreen button:** activado
- **Mobile friendly:** activado (se juega tocando la mitad de arriba = ↑ y la de abajo = ↓)
- **Scrollbars:** desactivado
- **Automatically start on page load:** desactivado (el audio necesita un clic primero)

## 4) Descripción (pegar tal cual)

```
Atrapado en la memoria RAM de tu computador, un conejo hecho de una sola línea solo sobrevive si aprende a oír: los graves levantan bloques, los agudos cuelgan aros… y la estática se lo come si pulsas tarde.

== CÓMO SE JUEGA ==
Sube una canción (mp3/wav) o prueba la demo. El juego analiza el sonido en tiempo real y crea los obstáculos a partir de él:

  ↑  /  Espacio  /  W   →  BLOQUE (graves)
  ↓  /  S                →  ARO (agudos)
  Móvil: toca la mitad de arriba = ↑, la de abajo = ↓

Pulsa justo cuando el obstáculo llegue al círculo del suelo. Mientras más justo, más puntos (PERFECT / BIEN / FALLO).

== LO QUE VAS A ENCONTRAR ==
* Tu música, tu nivel: la canción se analiza en tu navegador y no se sube a ningún servidor.
* Tres formas de Vibri según tus vidas: conejo (3), sapo (2) y oruga cabezona (1).
* Corona dorada con combo 30, y cada 30 aciertos recuperas una vida.
* Escenario 3D de líneas que gira 360° cada 3000 puntos.
* RAM que se sobrecalienta: si machacas las teclas, la pantalla se pone roja y te bloqueas unos segundos. Aquí gana quien escucha, no quien más rápido toca.
* Todo es vectorial: personajes, letras y escenario son líneas dibujadas con código.

== LA HISTORIA ==
Una madrugada, unos desarrolladores programaban con música a todo volumen. Un buffer de audio quedó sin liberar junto a un conejo de prueba, y nació Vibri: un proceso sin dueño que solo existe mientras suena música. Para seguir oyendo, salta de RAM en RAM, pero cada salto llena la memoria y arruina el trabajo del equipo. Los devs no pueden borrarlo, así que convierten su propia música en un laberinto de obstáculos. Historia completa en la página del juego: https://javoerito.github.io/Moviles-juego/#historia

== AVISOS ==
* Fotosensibilidad: la intro incluye estática de TV (≈1,5 s) y la pantalla parpadea suavemente en rojo cuando la RAM se sobrecalienta. La intro se salta con cualquier tecla o toque.
* Cuida el volumen de tus audífonos.
* Clasificación creativa E: apto para cualquier humano con pulso (y conejos con latencia). No oficial.
* Privacidad: sin cuentas, sin cookies, sin enviar datos. Tu canción nunca sale de tu navegador.

== CRÉDITOS ==
Concepto, código, arte vectorial y animaciones: Equipo ViboLínea (EPN).
Homenaje a Vib-Ribbon (NanaOn-Sha / Sony) y al arco del "malo con buen corazón" de Ralph el Demoledor (Disney). Sin afiliación.
Pista demo generada por código (Web Audio). La música que cargues pertenece a sus autores.
Código y textos elaborados con asistencia de IA (Claude, Anthropic), revisados por el equipo.

Web del proyecto: https://javoerito.github.io/Moviles-juego/
Código: https://github.com/Javoerito/Moviles-juego
```

## 5) Otros campos

- **Community:** Comments activados.
- **Genre secundario / Made with:** HTML5 / Canvas / JavaScript (Web Audio).
- **Inputs:** Keyboard, Touchscreen.
- **Multiplayer:** Ninguno · **Player count:** Single player.
- **Accessibility:** Configurable controls ✘ · Textos en pantalla ✔ · Aviso de fotosensibilidad en la descripción ✔.
- **AI generation disclosure:** **Yes** (el código, los textos y la portada se elaboraron con asistencia de IA y fueron revisados por el equipo).
- **Links (Metadata → Links):** agrega la web del proyecto y el repositorio de GitHub.

## 6) Capturas de pantalla (3 a 5; tómalas con Win+Shift+S)

1. La intro: zoom a la RAM o la estática de TV.
2. Vibri formándose o saludando sobre fondo negro.
3. Partida con un bloque llegando al círculo (muestra el escenario 3D).
4. Partida con el aro y el mensaje PERFECT.
5. La pantalla roja de "¡RAM SOBRECALENTADA!".
6. (Opcional) Vibri como sapo y como oruga cabezona, o la corona del combo 30.

## 7) Primer devlog (opcional, 30 segundos)

> **ViboLínea ya está en línea.** Es un juego de ritmo hecho de líneas que tiemblan: sube tu canción y el nivel nace de ella. Hecho para la clase de Móviles en la EPN. ¡Cuéntanos qué canción te hizo sufrir más!
