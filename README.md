# Jonas Blichfeldt · Portfolio

Kilden til jonasvestdesign.dk. Sitet bygges med [Eleventy](https://www.11ty.dev/) og udgives automatisk af Netlify, hver gang der pushes til `main`.

## Struktur

```
src/
  index.njk, om-mig.njk, …    én fil pr. side (kun sidens indhold)
  _includes/layouts/base.njk  fælles <head>, header, footer
  _includes/partials/         header, footer, rail og logo
  _data/site.json             navn, mail og LinkedIn ét sted
  css/site.css                fælles stilark
  css/pages/*.css             hver sides egne regler
  media/                      billeder og video
```

## Rette noget

- **Tekst på en side:** ret i `src/<side>.njk`.
- **Header, footer, mail eller LinkedIn:** ret i `src/_includes/partials/` eller `src/_data/site.json`, så slår det igennem på alle sider.
- **Farver og fælles design:** ret i `src/css/site.css`.

Små rettelser kan laves direkte på github.com (klik på filen → blyanten → *Commit changes*). Netlify udgiver selv den nye version efter et minut eller to.

## Ny case

1. Kopiér fx `src/fogi.njk` til `src/ny-case.njk` og ret `title`, `permalink` og `css` øverst.
2. Opret `src/css/pages/ny-case.css`.
3. Læg billeder og video i `src/media/`.
4. Tilføj et kort på forsiden i `src/index.njk`.

## Se sitet lokalt

```
npm install
npm start
```

Åbn derefter http://localhost:8080.
