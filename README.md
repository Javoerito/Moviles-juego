# * ViboLínea *

Juego de ritmo hecho de líneas que tiemblan. Sube tu canción: los graves levantan bloques (↑) y los agudos cuelgan aros (↓).
Proyecto académico, homenaje a *Vib-Ribbon*.

> **Logline:** Atrapado en la memoria RAM de tu computador, un conejo hecho de una sola línea solo sobrevive si aprende a oír: los graves levantan bloques, los agudos cuelgan aros… y la estática se lo come si pulsas tarde.

## Estructura del repositorio

```
├── index.html                    ← Landing page (Misión 3). Es lo que publica GitHub Pages
├── juego/
│   └── index.html                ← El juego completo (Canvas 2D nativo, un solo archivo)
├── .github/workflows/itch.yml    ← CI/CD a itch.io (Misión Legendaria)
├── itch/                         ← Kit para la página de itch.io (portada + textos para pegar)
├── .nojekyll                     ← Evita que GitHub Pages procese el sitio con Jekyll
├── LICENSE                       ← MIT
└── README.md
```

> Nota: el juego usa Canvas 2D nativo en vez de Phaser. La carpeta `juego/` cumple el mismo papel que la "subcarpeta del canvas de Phaser" del taller.

## Antes de publicar: checklist (5 minutos)

- [ ] En `index.html` (Muro de Honor) escribe los nombres reales del equipo.
- [ ] Cuando exista la página de itch.io: en `index.html`, dentro del `<script>`, pega el enlace en `const ITCH_URL = '';`.
- [ ] **Foto de la RAM de la intro** (`juego/index.html`, constante `RAM_SRC`): confirma de dónde salió. Si no es tuya o no tiene licencia que permita usarla, **reemplázala** por una foto propia o una con licencia CC0 / CC BY (y acredítala en el Muro de Honor).
- [ ] En `.github/workflows/itch.yml` cambia `ITCH_USER` e `ITCH_GAME`.
- [ ] Opcional: si no quieren ser tan literales con "homenaje a Vib-Ribbon", cambien el nombre del personaje (Vibri) antes de publicar en una plataforma pública.

## Misión 3: GitHub Pages

```bash
git init
git add .
git commit -m "ViboLínea: landing + juego"
git branch -M main
git remote add origin https://github.com/Javoerito/Moviles-juego.git
git push -u origin main
```

Luego en GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
En 1 o 2 minutos queda en `https://javoerito.github.io/Moviles-juego/` (el botón JUGAR lleva a `.../Moviles-juego/juego/`).

## Misión 4: tu hogar indie (itch.io)

1. Crea la cuenta gratis en itch.io y elige el nombre de tu "Estudio Indie".
2. **Create new project** → *Kind of project*: **HTML**.
3. Configuración sugerida:
   - **Title:** ViboLínea
   - **Short description:** Juego de ritmo hecho de líneas: sube tu canción y el nivel nace de ella.
   - **Classification:** Games · **Genre:** Rhythm · **Tags:** rhythm, music, vector, retro, minimalist, browser
   - **Pricing:** No payments (gratis)
   - **Embed options:** viewport 960×600, activar **Fullscreen button**, y **Mobile friendly** si lo van a probar en celular
   - **Age/legal:** copiar la clasificación creativa y el aviso de fotosensibilidad de la landing
4. Para la primera subida sin CI/CD: comprime la **carpeta `juego/`** de modo que `index.html` quede en la raíz del `.zip`, súbela y marca **"This file will be played in the browser"**.

## Misión Legendaria: CI/CD con GitHub Actions + butler

El archivo ya está en `.github/workflows/itch.yml`. Solo falta:

1. **API key:** itch.io → Settings → API keys → *Generate new API key*.
2. **Secret:** en GitHub → Settings → Secrets and variables → Actions → *New repository secret* → nombre `BUTLER_API_KEY`, valor = la key.
3. Edita `ITCH_USER` e `ITCH_GAME` en el YAML.
4. Haz push a `main` (o lánzalo a mano en la pestaña **Actions → Publicar en itch.io → Run workflow**).
5. Tras el primer push, en itch.io → *Edit game → Uploads* marca **"This file will be played in the browser"** en el archivo del canal `html5`.

Cómo funciona: cada push a `main` que toque `juego/` descarga butler (la herramienta oficial de itch.io), y ejecuta `butler push juego usuario/juego:html5`. Itch.io versiona solo; usamos el SHA corto del commit como versión.

## El Gran Final: mensaje para Teams (plantilla)

```
🎮 ViboLínea — Equipo [nombre]
1) Landing (GitHub Pages): https://javoerito.github.io/Moviles-juego/
   Juego directo:           https://javoerito.github.io/Moviles-juego/juego/
2) Plataforma indie: https://TU_USUARIO.itch.io/viblinea   ← pega aquí el enlace real
3) CI/CD (mención de honor): .github/workflows/itch.yml
   push a main → butler → itch.io en ~2 min
```

## Misión 1 y 2 (para el informe)

- **Logline:** ver arriba.
- **Resonancia ludonarrativa:** cada tecla responde "¿esto que oigo es grave o agudo?". El juego usa la FFT (Web Audio) y el *flujo espectral* para construir el nivel; el jugador aprende a distinguir frecuencias por reflejo. La salud de Vibri (conejo → sapo → oruga) representa la degradación de la señal, y el anti-spam premia escuchar en vez de adivinar.
- **Clasificación creativa:** "E: apto para cualquier humano con pulso (y para conejos con latencia)". No oficial.
- **Muro de Honor:** ver la landing. Si agregan assets de terceros (arte, sonido, fuentes), anótenlos con autor, fuente y licencia (CC0, CC BY, etc.).

## Licencia

MIT. La música que cargue cada jugador pertenece a sus autores y nunca sale del navegador.
