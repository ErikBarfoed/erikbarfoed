# erikbarfoed.dk

Erik Barfoeds forfatter-hjemmeside. Claude koder og vedligeholder; Erik bestemmer indhold og design.

## Claudes rolle

- Bygger og vedligeholder sitet (automation-projekt, jf. globale regler)
- Udkast til nyhedstekster (blogindlæg om udgivelser, anmeldelser, arrangementer) er tilladt — Erik redigerer og godkender altid. ALDRIG fiktion; al litterær tekst er Eriks
- Anmeldercitater skal være ordret — aldrig omskrives. Sammensatte citater limes med "..."
- Ingen emojis. Dansk sprog med æ, ø, å — også i commits og filnavne (dog ascii i URL-slugs: "boeger", "indlaeg")

## Arkitektur

- **Hugo** (statisk site) med eget tema i `themes/erikbarfoed-theme/` (ligger direkte i repoet, ikke submodule)
- **Deploy: GitHub Pages** via Actions (`.github/workflows/hugo.yml`) — hvert push til `main` bygger og deployer automatisk
- **Domæne:** erikbarfoed.dk — DNS hos Simply.com (fire A-records til GitHub Pages + www-CNAME til erikbarfoed.github.io). Mail kører via Simply (MX/DKIM/SPF) — rør aldrig mail-records
- **OBS: Repoet er public.** Alt, der committes, er offentligt synligt på GitHub. Arbejdsmateriale (fotos, skærmbilleder, udkast) ligger i `materiale/`, som er gitignoret
- **Disciplin i committede filer:** Følsomme detaljer (tal, økonomi, upublicerede planer, personlige oplysninger) hører til i `materiale/` eller memory — aldrig i CLAUDE.md, project.md eller sitets indhold
- Netlify blev forladt august 2026 (credit-baseret prismodel); kontoen er nedlagt, og `netlify.toml` er fjernet

## Struktur

- `content/boeger/` — én fil pr. bog; anmeldercitater i frontmatter (`reviews:` med `quote`/`source`)
- `content/indlaeg/` — nyheder/blog; forsiden viser de 5 nyeste automatisk. Brug `<!--more-->` som teaser-skille
- `content/presse.md` — omtaler, anmeldelser pr. bog, pressebilleder. Nyeste øverst i alle sektioner
- `static/images/` — billeder (publiceres på sitet)

## Arbejdsgang

- Test lokalt: `hugo -d <scratchpad>` (Hugo er installeret via Homebrew)
- Push kun efter Eriks godkendelse — push er publicering
- Tekstændringer: Erik godkender ordlyd før publicering
