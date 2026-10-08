# Projektregler for jvb-portfolio

Jonas' portfolio til design- og reklamebureauer. Alt indhold er på dansk.

## Arbejdsgang
- Ret i `src/`, aldrig i `_site/` (genereres af Eleventy).
- Byg med `npx eleventy` og tjek siderne i en browser før push. Netlify udgiver `main` automatisk.

## Design (låst)
- Farver: aubergine `#20011D` og hvid. Skrifter: Bricolage Grotesque (display) og Hanken Grotesk (brødtekst).
- Kun ét rundet hjørne pr. element (`.r-tl/.r-tr/.r-bl/.r-br`), varieret efter placering.
- `.reveal` må aldrig sidde direkte på interaktive elementer (knapper, links med hover). Læg den på en wrapper, ellers overskrives elementets transition.
- Skygger skal fade fra gennemsigtig farve, ikke fra `none`.
- Knapper bruger fill-sweep-hover som `.cta` (fyld fra venstre, hvid tekst, to modstående hjørner rundes).
- Progress-rail'en vises kun fra 1320 px bredde.

## Tekst og tone
- Skriv som Jonas: ligeud, jordnært, forklar hvorfor, ingen selvros. Lad kundens reaktion tale.
- Startkomma, ingen tankestreger (—) i brødtekst, almindelige citationstegn ("…").
- Ingen punchlines til sidst i afsnit og ingen "ikke X, men Y"-retorik, medmindre det er Jonas' egne ord.
- Vær præcis om fordeling af arbejdet: skriv kun det, Jonas selv har lavet, som hans.

## Fakta der er rettet før
- Hvidt & Frit forår 2026: landsdækkende tilvalgskampagne for butikkerne (ikke sommer). "Råd til mere dage" er kædens store kampagne.
- FOGI: Cambria er kundens primære font. Format 210 × 250 mm. Faktaboksen på s. 25 har et buet indhak.
- Jonas vandt DM i Skills 2024 og fik 12 til svendeprøven.

## Deling og SEO
- Hver side har `description` og `ogImage` i front matter. Base-layoutet laver meta description, canonical og Open Graph-tags ud fra dem og `site.url` i `src/_data/site.json`.
- Delingsbillederne er statiske filer på 1200 × 630 i `src/media/share-*.jpg`, lavet i sitets stil (Bricolage-titel til venstre, værket til højre med ét rundet hjørne). Ny case = nyt delingsbillede.
- `src/404.njk` er sitets 404-side. Netlify bruger den automatisk.

## Kendte faldgruber
- Flex-rækker med `flex-basis:0` og `overflow:hidden` falder sammen til 0 i højden, når de skiftes til `flex-direction:column` på mobil. Sæt `flex:none` i mobil-reglen (se fotogalleriet).
- Tjek altid 360, 390, 768, 1024 og 1440 px. Tablet på højkant er hvor to-kolonne-layouts typisk knækker.
