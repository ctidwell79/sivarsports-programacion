# sivarsports-programacion

Sitio estático de **Programación Oficial** para SIVAR Sports Academy + CTC BKB Club.

**Producción:** https://programacion.sivarsports.com
**Hosted on:** Netlify (Kamay Group team) → repo `ctidwell79/sivarsports-programacion`

## ¿Qué es esto?

Página pública con la programación de juegos y torneos (LD Apertura 2026, FESABAL, Torneo Mini, etc.) filtrable por fecha y por equipo (SIVAR / CTC, U12–U18 M/F). Mobile-first, sin backend.

## Cómo actualizar la programación

La lista de juegos vive como un array JS dentro de `index.html`. Para agregar/cambiar juegos:

1. Abrir `index.html` en cualquier editor.
2. Buscar el array `const games = [` (≈ línea 626).
3. Cada juego es un objeto con esta forma:

```js
{
  date: '2026-05-09',          // YYYY-MM-DD
  day: 'Sábado',                // Lunes / Martes / ... / Domingo
  cat: 'U12F',                  // U12F / U12M / U14F / U14M / U16F / U16M / U18F / U18M
  teamA: 'SIVAR SPORTS ACADEMY',
  teamB: 'Guerreros',
  time: '8:00 a.m.',
  timeSort: 800,                // hora en formato HHMM (24h) — 800 = 8:00am, 1300 = 1pm, 1645 = 4:45pm
  venue: 'Cancha Chapupo',
  competition: 'TORNEO MINI'    // 'FESABAL LD' | 'TORNEO MINI' | etc.
}
```

4. Commit + push a `main`. Netlify auto-deploya en ~30 segundos.

### Tips

- Para que el card resalte en coral, uno de los equipos debe ser exactamente `SIVAR SPORTS ACADEMY` (mayúsculas).
- Para CTC, usar exactamente `CTC BKB CLUB`.
- El badge de competencia es navy si dice `FESABAL LD`, gradient rosa para cualquier otro valor (Torneo Mini, etc.).
- `timeSort` se usa solo para ordenar — debe ser HHMM en 24h.

## Stack

- HTML + CSS + JS vanilla, single file.
- Fonts: Bebas Neue / Archivo / JetBrains Mono via Google Fonts.
- Sin build step, sin dependencias, sin backend.
- Netlify publica `/` directo (sin `npm run build`).

## DNS

- `programacion.sivarsports.com` → CNAME → `sivarsports-programacion.netlify.app`
- Cert: Let's Encrypt, auto-renew vía Netlify.

## Marca

- Navy `#1E2D58` · Coral `#E8607A` · Bone `#f4f1ea` (paleta CTC).
- Lema: **Campeones Trabajan Como Campeones**.
