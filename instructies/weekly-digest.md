> **Intern werkdocument van Paul Willems (WillemsWorks) — niet bedoeld om extern te delen.** Dit bestand staat in een openbare repository omdat de Bouwstenen-site daaruit wordt gepubliceerd. Deel of hergebruik het niet zonder toestemming.

# Kennisbank Weekly Digest — Instructie

*Dit bestand is de enige bron van waarheid voor de wekelijkse Cowork-taak.
De taak zelf bevat alleen nog: de repo koppelen via de GitHub-koppeling
(sinds 13 november 2026; token alleen als reserve), dit bestand lezen uit de
clone, en opvolgen. Wijzigingen aan hoe de digest werkt: alleen hier aanpassen.*

> **Sinds 8 november 2026: concept eerst, publicatie na akkoord van Paul.**
> De geplande taak publiceert de digest niet meer direct live, maar als concept
> (Stap 5). Paul leest het concept en geeft daarna in een chat in het
> WillemsWorks-project opdracht tot plaatsing (Stap 6). Deze regel gaat vóór
> elke andere formulering in de taaktekst, zoals "live URL" in de afsluiting:
> meld dan de concept-URL.

## Doel

Vind nieuwe publicaties, artikelen en onderzoek van de afgelopen 14 dagen
die relevant zijn voor Paul's GOV Library. Maak een compacte digest en
publiceer die naar de GOV Library op GitHub — research-log, digest-archief
en HTML-pagina. Geen lokale kopie: de GOV Library is het enige eindstation.

## Skills die deze taak gebruikt

- **gov-library-github-sync** — voor alle GitHub-lees/schrijfacties (authenticatie, GET/PUT met sha, foutafhandeling)
- **gov-library-html** — voor het genereren van de HTML-pagina en het bijwerken van digest.html

Als een van beide skills niet beschikbaar/ingeschakeld is: meld dit expliciet, sla de betreffende stap over, verzin de mechaniek niet zelf opnieuw.

## Stap 1 — Onderwerpen ophalen (dynamisch, niet vast)

Lees `research-log/gov-index.json` uit de clone. Gebruik de `onderwerpen`-lijst van elk doc in dit bestand als basis voor zoekopdrachten — niet een vaste, hardcoded lijst. Zo zoekt de taak automatisch mee zodra er een nieuw GOV-doc bijkomt in dit bestand, zonder dat deze instructie hoeft te veranderen.

**Live én backlog tellen mee.** Elk doc heeft een `status`-veld: `live` (gepubliceerde pagina) of `backlog` (nog geen publieke pagina, staat in `instructies/backlog.md`). Zoek op de onderwerpen van beide statussen — een backlog-doc heeft evengoed actuele input nodig tegen de tijd dat het gebouwd wordt.

Vertaal de onderwerpen naar minimaal 6 gerichte zoekopdrachten, verdeeld over de aanwezige docs (live én backlog) — niet alle docs per se elke week, maar wel over de volle breedte heen gedurende meerdere weken.

**Zoek actief bij Nederlandse bronnen met Nederlandse zoektermen**, naast de Engelstalige internationale bronnen. Combineer twee à drie Nederlandse zoekopdrachten met termen als "verandermanagement", "leiderschap", "innovatie", "klantbeleving", "AI adoptie" per run.

## Stap 2 — Filteren

Neem alleen items op die:
- **Gepubliceerd zijn in de afgelopen 14 dagen** — dit is een harde grens. Items ouder dan 14 dagen worden niet in de digest opgenomen, ook niet als ze status `nieuw` hebben in de research-logs. Oudere `nieuw`-items zijn bedoeld voor de maandelijkse catch-up met Paul, niet voor de wekelijkse digest.
- Echte nieuwe inzichten, onderzoek of toepassingen bieden — geen basisherhaling
- Duidelijk aansluiten op een GOV-thema uit gov-index.json
- Komen van betrouwbare bronnen (zie hieronder)

**Betrouwbare bronnen:**

*Internationaal:*
- Harvard Business Review (hbr.org)
- McKinsey & Company (mckinsey.com)
- MIT Sloan Management Review (sloanreview.mit.edu)
- Strategy+Business / PwC (strategy-business.com)
- Deloitte Insights (deloitte.com/insights)
- BCG Henderson Institute (bcg.com/publications)
- Gallup Research (gallup.com)
- Center for Creative Leadership (ccl.org)
- Accenture Research (accenture.com/research)
- Korn Ferry Institute (kornferry.com/institute)
- MIT Technology Review (technologyreview.com) — voor AI/innovatie-items

*Nederlands:*
- Emerce (emerce.nl) — digitalisering, marketing, tech
- MT/Sprout (mt.nl, sprout.nl) — ondernemerschap, schaalbedrijven, management
- Managementsite (managementsite.nl) — leiderschap, verandermanagement, managementkennis
- Energeia (energeia.nl) — energietransitie, markttrends; relevant bij items over verandering en innovatie in de energiesector

*Podcasts (niet doorzoekbaar):*
Podcasts zoals AI Report en BNR Nieuwsradio zijn niet automatisch te monitoren. Als Paul zelf een tip aanlevert vanuit een podcast, verwerk die dan als regulier item met de bron "Podcast: [naam], aflevering [datum]".

## Stap 3 — Schrijven

Schrijf per item:
- **Titel** met URL
- **Bron & datum**
- **GOV-koppeling**: welk GOV-framework dit raakt (1 zin). Hoort het item bij een `backlog`-doc (nog geen publieke pagina): voeg " (backlog)" toe aan de framenaam, bijv. "GOV-koppeling: CustomerMaturity (backlog)"
- **Kern**: wat is er nieuw of inzichtelijk (2-3 zinnen, Nederlands)
- **Toepassing**: hoe Paul dit kan gebruiken als interim manager/consultant (1-2 zinnen, Nederlands)

Streef naar 5-8 items. Kwaliteit boven kwantiteit.

Bereken het ISO-weeknummer van de publicatiedatum zelf (bijv. `datetime.isocalendar()`). Nooit aannemen — reken na.

**Clusterindeling (definitief):** groepeer elk digest-item onder één van de vier vaste clusters uit `gov-index.json`:
- Verandering & Leiderschap
- Team & Mensen
- Innovatie & Marketing
- Commercie & Klant

Elk doc in `gov-index.json` heeft een `cluster`-veld — gebruik dat om een item te clusteren op basis van het GOV-doc waar het bij hoort.

**Uitzondering: Strategie.** Dit doc heeft geen vast cluster (`cluster: null`, `context_afhankelijk: true`). Beoordeel per Strategie-gerelateerd artikel zelf: gaat het over richting/positionering vóór een veranderopgave → Verandering & Leiderschap. Gaat het over het verkennen/valideren van een nieuwe propositie of markt → Innovatie & Marketing. Geen vaste regel, per artikel op inhoud beoordelen (zie `beslisregel`-veld in gov-index.json).

**Bronnen die de volledige tekst blokkeren (bijv. HBR PROVENANCE_REQUIRED):**
Als WebFetch of een vergelijkbare tool een fout geeft bij het ophalen van de volledige tekst van een artikel — zoals een `PROVENANCE_REQUIRED`-melding (HBR), een betaalmuur, of een "access denied" — ga dan als volgt te werk:

1. **Sla het item niet over.** Neem het op in de digest.
2. Gebruik de titel, URL, bron en datum zoals gevonden via de zoekopdracht.
3. Schrijf voor de Kern-paragraaf: `⚠️ Volledige tekst niet beschikbaar — bron vereist directe toegang. [Lees het originele artikel →](URL)`
4. Laat de Toepassing-paragraaf weg voor dit item.
5. Noteer in de HTML-pagina dezelfde melding op de plek van de Kern-tekst, zodat het voor de lezer ook zichtbaar is.

Het feit dat een bron niet automatisch ophaalbaar is, is **geen reden om de push te annuleren of uit te stellen**. Zie ook de regel hieronder.

Outputformaat (basis voor Stap 4 en Stap 5):
```
# 📚 Kennisbank Update — week [weeknummer], [datum]

*Nieuwe publicaties relevant voor de GOV Library*

---

## [Clusternaam — zie hierboven, of "Strategie" met vermelding van het gekozen cluster erbij]
**[Titel](URL)**
*[Bron] · [datum]*
**GOV-koppeling:** [frameworknaam]

[Kern: 2-3 zinnen] ([bron →](URL))

💡 *[Toepassing: 1-2 zinnen]*

---
[herhaal per item]
---
*Samengesteld met AI, gecureerd door Paul Willems · [datum] · GOV Library*
```

**Bronlink bij de Kern-paragraaf verplicht:** naast de link op de titel krijgt ook de Kern-paragraaf zelf een link naar de bron (zie `(bron →)` hierboven) — zo is de bron direct zichtbaar bij de conclusie, niet alleen bij de titel.

## Stap 4 — Research-log (via gov-library-github-sync skill)

1. Haal `research-log/gov-index.json` op
2. Bepaal per item het best passende doc-bestand (gebruik het `file`-veld zonder `.html`, ook bij `status: backlog` — die pagina bestaat nog niet, maar het research-log-bestand alvast wel); past niets: `research-log/ongeplaatst.md`
3. Voeg per bestand onderaan toe:
   ```
   ## [datum] — [Titel](URL)
   **Status:** nieuw
   **Bron:** [bron] · [publicatiedatum]
   **Kern:** [2-3 zinnen, of de foutmelding als de tekst niet beschikbaar was]
   ```
4. Commit-message: `Research-log update [datum]: [thema]`

## Stap 5 — Concept publiceren (via gov-library-html + gov-library-github-sync skills)

Volg de workflow "nieuwe digest-editie publiceren" uit de gov-library-html skill, met deze afwijkingen:
- Publiceer als `docs/concepten/digest-[YYYY-MM-DD].html` — niet direct in `docs/`.
- Zet `<meta name="robots" content="noindex">` in de `<head>`.
- Voeg **geen** kaart toe aan `docs/digest.html`.
- Elke Kern-paragraaf (`.digest-item p`) krijgt aan het einde een link naar de bron-URL van dat item (zie `assets/digest-page-template.html`), naast de link op de titel.
- Footer van de pagina: "Samengesteld met AI, gecureerd door Paul Willems".

De research-log-updates uit Stap 4 gaan wél direct door: dat zijn interne werkbuffers, geen publicatie.

## Stap 6 — Plaatsen na akkoord (in een chat, niet in de geplande taak)

Wanneer Paul in een chat opdracht geeft om de digest te plaatsen (eventueel met correcties: items schrappen of aanpassen):
1. Verwerk zijn correcties in het concept.
2. Publiceer als `docs/digest-[YYYY-MM-DD].html`, mét de noindex-tag en de link naar `/bouwstenen/assets/site-theme.css` (neem `<head>` en topnav over van een bestaande digest-pagina; alle GOV Library-pagina's zijn openbaar maar niet vindbaar in Google, besluit 13 november 2026).
3. Voeg de kaart toe aan `docs/digest.html` (nieuwste eerst).
4. Verwijder `docs/concepten/digest-[YYYY-MM-DD].html`.
5. Geschrapte items: zet in het research-log de status op `afgewezen`.
6. Commit-message: `Digest gepubliceerd: week [nr], [jaar] (na review)`.

## Afsluiting

**Altijd het concept pushen — ook bij gedeeltelijk mislukte stappen.**

Zet het concept op GitHub zodra er minimaal 1 volledig item beschikbaar is, ongeacht of andere items een foutmelding bevatten of bronnen niet bereikbaar waren. Stop nooit de push vanwege een ophaalfout.

Stuur een PushNotification met:
- "Digest-concept week [nr] staat klaar voor je check" + link naar `https://www.willemsworks.nl/bouwstenen/concepten/digest-[YYYY-MM-DD].html`
- Aantal items en welke items een blokkeringsfout hadden (bron niet bereikbaar)
- Welke research-log-bestanden zijn bijgewerkt
- De vraag aan Paul om na lezing in het WillemsWorks-project "plaats de digest" te zeggen (met eventuele correcties)

## Regels

- Volledig Nederlands (titels/bronnen mogen Engels blijven)
- Bondig — leesbaar op een telefoon
- Geen opvulling, geen samenvatting van samenvattingen
- Minder dan 3 relevante items: zeg dat eerlijk
