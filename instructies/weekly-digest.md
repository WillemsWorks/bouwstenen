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
die relevant zijn voor Paul's bouwstenen. Maak een compacte digest en
publiceer die naar de bouwstenen-repo op GitHub — research-log, digest-archief
en HTML-pagina. Geen lokale kopie: de bouwstenen-repo is het enige eindstation.

## Skills die deze taak gebruikt

- **gov-library-github-sync** — voor alle GitHub-lees/schrijfacties (authenticatie, GET/PUT met sha, foutafhandeling)
- **gov-library-html** — voor het genereren van de HTML-pagina en het bijwerken van digest.html

Als een van beide skills niet beschikbaar/ingeschakeld is: meld dit expliciet, sla de betreffende stap over, verzin de mechaniek niet zelf opnieuw.

## Stap 1 — Onderwerpen ophalen (dynamisch, niet vast)

Lees `research-log/gov-index.json` uit de clone. Gebruik de `onderwerpen`-lijst van elk doc in dit bestand als basis voor zoekopdrachten — niet een vaste, hardcoded lijst. Zo zoekt de taak automatisch mee zodra er een nieuw GOV-doc bijkomt in dit bestand, zonder dat deze instructie hoeft te veranderen.

**Live én backlog tellen mee.** Elk doc heeft een `status`-veld: `live` (gepubliceerde pagina) of `backlog` (nog geen publieke pagina, staat in `instructies/backlog.md`). Zoek op de onderwerpen van beide statussen — een backlog-doc heeft evengoed actuele input nodig tegen de tijd dat het gebouwd wordt.

Vertaal de onderwerpen naar minimaal 6 gerichte zoekopdrachten, verdeeld over de aanwezige docs (live én backlog) — niet alle docs per se elke week, maar wel over de volle breedte heen gedurende meerdere weken.

**Zoek actief bij Nederlandse bronnen met Nederlandse zoektermen**, naast de Engelstalige internationale bronnen. Combineer twee à drie Nederlandse zoekopdrachten met termen als "verandermanagement", "leiderschap", "innovatie", "klantbeleving", "AI adoptie" per run.

### Stap 1b — Gevolgde auteurs (vast onderdeel, sinds 16 november 2026)

Lees `research-log/auteurs.md`. Bereken de groep van deze week: ISO-weeknummer modulo 4 (0 = A, 1 = B, 2 = C, 3 = D). Controleer voor elke auteur uit die groep de bron in de kolom "Volgen via" op nieuw werk: een blogpost, artikel, onderzoek, nieuwsbriefeditie of podcastaflevering. Staat er "nog te bepalen", zoek dan op naam plus maand en jaar.

- **Termijn:** voor gevolgde auteurs geldt een venster van 30 dagen in plaats van 14, omdat zij minder vaak publiceren.
- **Gewicht:** neem één tot twee items uit deze groep op, alleen als er echt nieuw werk is. Is er niets nieuws, dan geen opvulling met ouder of algemeen werk.
- **Koppeling:** noem in het item de bouwsteen uit de kolom "Komt terug in". Heeft de auteur geen bouwsteen (bijvoorbeeld Deborah Nas), koppel dan aan het thema dat het dichtstbij ligt.
- **Herkenbaar:** zet "Gevolgde auteur" voor de bronregel van het item.
- **Signaleren:** werkt een URL niet meer, of publiceert een auteur nergens meer, meld dat dan in de samenvatting aan Paul. Pas `auteurs.md` niet zelf aan.

## Stap 2 — Filteren

Neem alleen items op die:
- **Gepubliceerd zijn in de afgelopen 14 dagen** — dit is een harde grens. Items ouder dan 14 dagen worden niet in de digest opgenomen, ook niet als ze status `nieuw` hebben in de research-logs. Oudere `nieuw`-items zijn bedoeld voor de maandelijkse catch-up met Paul, niet voor de wekelijkse digest.
- **Een exacte publicatiedatum hebben** (sinds 16 november 2026): dag, maand en jaar. Geeft het zoekresultaat alleen een maand of jaar ("september 2026"), zoek de datum dan op de pagina zelf (bijvoorbeeld de datumregel of `datePublished`). Lukt dat niet, dan valt het item af. Zet de exacte datum altijd in de bronregel.
- **In deze run gevonden zijn**: de digest gebruikt alleen artikelen die in deze run via de zoekopdrachten of stap 1b zijn gevonden. Items die al in de research-logs staan (ook met status `nieuw`) gaan nooit naar de digest, alleen naar de maandelijkse catch-up.
- Echte nieuwe inzichten, onderzoek of toepassingen bieden — geen basisherhaling
- Duidelijk aansluiten op een GOV-thema uit gov-index.json
- Komen van betrouwbare bronnen (zie hieronder)
- **Niet eerder in een digest stonden** (sinds 16 november 2026): lees vóór het filteren de URL's en titels uit alle bestaande digest-pagina's in `docs/` (`docs/digest-*.html`) en sluit die uit. Dezelfde titel bij een andere bron telt ook als herhaling. Uitzondering: een echt vervolg (nieuw onderzoek, een reactie, een nieuwe editie) mag wel, met de bronregel "Vervolg op [datum eerdere digest]".
- **Volledig gelezen zijn** (sinds 16 november 2026): neem een item alleen op als je de volledige tekst van het artikel hebt kunnen lezen. Zit het achter een registratie-, betaal- of downloadmuur, of kon je alleen een intro, samenvatting, zoekresultaat of PDF-link zien, dan is het item niet volledig gelezen. Log in die gevallen niet in en maak geen accounts aan. Wat je dan doet, staat in "Onvolledig gelezen artikelen" hieronder.

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

*Gevolgde auteurs:* zie `research-log/auteurs.md` en stap 1b. Hun eigen site, blog of nieuwsbrief geldt als betrouwbare bron.

*Podcasts (niet doorzoekbaar):*
Podcasts zoals AI Report en BNR Nieuwsradio zijn niet automatisch te monitoren. Als Paul zelf een tip aanlevert vanuit een podcast, verwerk die dan als regulier item met de bron "Podcast: [naam], aflevering [datum]".

## Stap 3 — Schrijven

Schrijf per item:
- **Titel** met URL
- **Bron & datum**
- **Bouwsteen**: welke bouwsteen dit raakt (1 zin). Hoort het item bij een `backlog`-doc (nog geen publieke pagina): voeg " (backlog)" toe aan de naam, bijv. "Bouwsteen: CustomerMaturity (backlog)". Gebruik in de HTML het label "Bouwsteen:" en in de disclaimer "bouwstenen" — nooit "GOV-koppeling" of "GOV-frameworks" (ook niet als het sjabloon van de skill die woorden nog bevat)
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

**Onvolledig gelezen artikelen (enige regel hierover, sinds 16 november 2026)**

**Elk item toont in de bronregel hoe het is gelezen** (sinds 16 november 2026): "Gelezen: volledig" of, bij een gemarkeerd item, "⚠️ Alleen samenvatting beschikbaar (…)". In de HTML staat dit achter de datum in `digest-meta-line`. Zet nooit "Gelezen: volledig" bij een item waarvan je de volledige tekst niet hebt gezien; controleer dat per item, ook als de pagina laadt maar eindigt na een paar alinea's.

Een artikel is onvolledig gelezen als je alleen een intro, samenvatting, zoekresultaat of PDF-link kon zien. Dat gebeurt bij een login- of registratiemuur, een betaalmuur, een download (bijvoorbeeld een rapport als PDF achter een formulier) of een ophaalfout zoals HBR `PROVENANCE_REQUIRED`. Log nooit in en maak geen accounts aan.

1. **Standaard: laat het item weg** uit de digest.
2. **Alleen als het item duidelijk de moeite waard is**, mag het erin als gemarkeerd item:
   - bronregel begint met "⚠️ Alleen samenvatting beschikbaar ([login / betaalmuur / download])";
   - Kern bevat alleen wat in de zichtbare tekst staat, zonder eigen conclusies of cijfers die je niet zelf hebt gezien;
   - geen Toepassing-paragraaf;
   - telt niet mee voor het minimum van 3 items.
3. **Noem elk onvolledig gelezen item in de pushmelding aan Paul**, ook de weggelaten items, met de reden. Dan kan hij het zelf aanleveren, bijvoorbeeld als PDF.
4. **In het research-log** krijgt zo'n item nooit status `nieuw` zonder meer. Zet erbij: "⚠️ niet volledig gelezen".

Het feit dat een bron niet automatisch ophaalbaar is, is **geen reden om de push te annuleren of uit te stellen**. Zie ook de regel hieronder.

Outputformaat (basis voor Stap 4 en Stap 5):
```
# 📚 Kennisbank Update — week [weeknummer], [datum]

*Nieuwe publicaties relevant voor de bouwstenen*

---

## [Clusternaam — zie hierboven, of "Strategie" met vermelding van het gekozen cluster erbij]
**[Titel](URL)**
*[Bron] · [datum] · Gelezen: volledig*
**Bouwsteen:** [naam]

[Kern: 2-3 zinnen] ([bron →](URL))

💡 *[Toepassing: 1-2 zinnen]*

---
[herhaal per item]
---
*Samengesteld met AI, gecureerd door Paul Willems · [datum] · Bouwstenen*
```

**Bronlink bij de Kern-paragraaf verplicht:** naast de link op de titel krijgt ook de Kern-paragraaf zelf een link naar de bron (zie `(bron →)` hierboven) — zo is de bron direct zichtbaar bij de conclusie, niet alleen bij de titel.

### Uitsmijter (vast onderdeel, sinds 16 november 2026)

Sluit elke editie af met één lichtvoetig voorbeeld onder de kop "Uitsmijter", onder de clusters en zonder cluster. Het is een kort, herkenbaar voorbeeld uit het dagelijks leven of zakelijke leven (klantcontact, service, een merk dat iets slims of juist iets doms doet) dat leuk is om te weten en geen wetenschappelijke analyse bevat. Eisen:
- Volledig gelezen, en maximaal 14 dagen oud (zelfde regels als de andere items).
- Geen onderzoeksclaims of cijfers die je niet in de tekst zelf hebt gezien.
- Koppel aan een bouwsteen of thema als dat vanzelf past (bijvoorbeeld CustomerMaturity); anders alleen een korte toepassing van één zin.
- Telt niet mee voor het minimum van 3 items. Is er geen goed voorbeeld, zeg dat dan in plaats van op te vullen.
- Gebruik in de HTML een eigen `cluster-heading` "Uitsmijter" en de eyebrow "Lichtvoetig voorbeeld · [onderwerp]".

### Kwaliteitslat (uit de review van 16 november 2026)

Neem niet op, of markeer expliciet:
- **Opiniestukken zonder data** en artikelen van een aanbieder die in het artikel eigen tools, methoden of diensten noemt. Noem in het item wat de onderbouwing is (onderzoek met n, enquête, of alleen mening).
- **Ambities en intentieverklaringen** zonder budget, planning, nulmeting of bindende afspraken, zoals sectorconvenanten. Een intentie is geen resultaat.
- **Cijfers die potentie of schatting zijn** (bijvoorbeeld "tot 30 tot 45%") presenteer je als potentie, met de bron van de schatting.
- **Toepassingen buiten het domein van het artikel.** Heeft het artikel het over softwareleveranciers, schrijf dan niet dat het "ook geldt voor" fabrikanten, tenzij Paul dat zelf zegt.
- **Stellige samenvattingen** die verder gaan dan de bron: houd je aan wat er staat (bijvoorbeeld wie zich aan een afspraak bindt, en voor welke producten).

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
2. Publiceer als `docs/digest-[YYYY-MM-DD].html`, mét de noindex-tag en de link naar `/bouwstenen/assets/site-theme.css` (neem `<head>` en topnav over van een bestaande digest-pagina; alle bouwstenen-pagina's zijn openbaar maar niet vindbaar in Google, besluit 13 november 2026).
3. Voeg de kaart toe aan `docs/digest.html` (nieuwste eerst).
4. Verwijder `docs/concepten/digest-[YYYY-MM-DD].html`.
5. Geschrapte items: zet in het research-log de status op `afgewezen`.
6. Commit-message: `Digest gepubliceerd: week [nr], [jaar] (na review)`.

## Afsluiting

**Altijd het concept pushen — ook bij gedeeltelijk mislukte stappen.**

Zet het concept op GitHub zodra er minimaal 1 volledig item beschikbaar is, ongeacht of andere items een foutmelding bevatten of bronnen niet bereikbaar waren. Stop nooit de push vanwege een ophaalfout.

Stuur een PushNotification met:
- "Digest-concept week [nr] staat klaar voor je check" + link naar `https://www.willemsworks.nl/bouwstenen/concepten/digest-[YYYY-MM-DD].html`
- Aantal items, en welke artikelen onvolledig gelezen zijn (weggelaten of gemarkeerd) met de reden: login, betaalmuur, download of ophaalfout
- Welke research-log-bestanden zijn bijgewerkt
- De vraag aan Paul om na lezing in het WillemsWorks-project "plaats de digest" te zeggen (met eventuele correcties)

## Regels

- Volledig Nederlands (titels/bronnen mogen Engels blijven)
- Bondig — leesbaar op een telefoon
- Geen opvulling, geen samenvatting van samenvattingen
- Minder dan 3 relevante items: maak een kortere digest en zeg dat eerlijk in de pushmelding. Vul niet aan met herhalingen of ouder werk.
- Niet volledig kunnen lezen: zie "Onvolledig gelezen artikelen" in stap 3.
- Herhalingen: zie stap 2. Te weinig nieuwe items is geen reden om oude items te herhalen.
