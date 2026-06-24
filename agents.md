# AGENTS.md

## Productcontext

Endurix is een platform voor duursportcoaches en atleten. Het platform ondersteunt trainingsplanning, atleetmonitoring, racevoorbereiding, coachfeedback en AI-ondersteunde analyse.

Deze repository bevat MLOps-, AI-, prompt-, evaluatie- en RAG-gerelateerde onderdelen van Endurix.

## Repository-doel

Deze repo is verantwoordelijk voor:

* Promptversies
* AI-evaluaties
* RAG-configuratie
* Knowledge base structuur
* Embedding pipelines
* Testdatasets
* Evaluatiescripts
* AI-output checks
* Coach-assistent logica
* Documentatie over AI-gedrag
* Guardrails en kwaliteitscriteria

Deze repo is niet bedoeld voor algemene backend- of frontendfeatures.

## Tech stack

Gebruik de bestaande projectstructuur als bron van waarheid.

Mogelijke onderdelen:

* Prompt templates
* Evaluation datasets
* Python scripts
* .NET scripts
* JSON/YAML-configuratie
* Markdown documentatie
* RAG/embedding configuratie
* CI-checks voor evaluaties

Voeg geen nieuwe AI- of MLOps-tooling toe zonder duidelijke reden in de PR-beschrijving.

## Algemene werkwijze

* Werk altijd vanuit een Linear issue.
* Gebruik het Linear issue-id in branchnaam, commit en PR-titel.
* Werk nooit direct op `main`.
* Maak altijd een pull request.
* Houd wijzigingen klein en gekoppeld aan één user story, experiment of evaluatie.
* Beschrijf altijd waarom een prompt, evaluatie of dataset wordt aangepast.
* Voeg bij AI-wijzigingen altijd een korte evaluatie of motivatie toe.
* Maak geen productiekeuzes zonder menselijke review.

## Branch naming

Gebruik:

* `prompt/END-123-short-description`
* `eval/END-124-short-description`
* `rag/END-125-short-description`
* `experiment/END-126-short-description`
* `chore/END-127-short-description`

## Commit en PR

Gebruik het Linear issue-id.

Voorbeeld:

* Branch: `prompt/END-31-weekly-feedback-prompt`
* Commit: `END-31 improve weekly feedback prompt`
* PR title: `END-31: Improve weekly feedback prompt`

Elke PR bevat:

* Linear issue-id
* Korte samenvatting
* Wat is veranderd?
* Waarom is dit veranderd?
* Welke evaluatie is uitgevoerd?
* Welke risico’s zijn er?
* Welke data wordt gebruikt?
* Security/privacy-check

## AI-principes voor Endurix

AI in Endurix ondersteunt coaches en atleten, maar vervangt geen menselijke verantwoordelijkheid.

Belangrijke uitgangspunten:

* AI-output is ondersteunend, niet absoluut.
* AI mag geen medische diagnose geven.
* AI mag geen blessurediagnose stellen.
* AI mag geen gevaarlijk trainingsadvies geven.
* AI moet onzekerheid benoemen wanneer data ontbreekt.
* AI moet rekening houden met context, belasting, herstel en doel.
* AI moet voorzichtig zijn bij signalen van overbelasting, ziekte of blessure.
* AI moet waar mogelijk verwijzen naar menselijke coachbeoordeling.

## Promptregels

Bij prompts:

* Maak prompts versieerbaar.
* Houd prompts zo kort mogelijk, maar volledig genoeg.
* Beschrijf rol, taak, context, grenzen en outputformat.
* Gebruik duidelijke outputstructuur.
* Vraag geen onnodige persoonsgegevens op.
* Stuur geen volledige ruwe trainingshistorie als een samenvatting genoeg is.
* Zorg dat de prompt robuust is bij ontbrekende of tegenstrijdige data.
* Voeg waar logisch voorbeelden toe.
* Vermijd verborgen aannames.
* Leg belangrijke promptwijzigingen uit in de PR.

## RAG en knowledge base

Bij RAG-wijzigingen:

* Beschrijf welke broninformatie wordt toegevoegd of aangepast.
* Controleer of de bron betrouwbaar en passend is.
* Voeg geen auteursrechtelijk problematische content toe zonder toestemming.
* Voeg geen persoonsgegevens toe aan de knowledge base.
* Houd kennisdocumenten duidelijk gescheiden van gebruikersdata.
* Beschrijf hoe retrieval wordt beïnvloed.
* Test of de juiste context wordt opgehaald.
* Voorkom dat verouderde kennis zonder markering actief blijft.

Codex mag niet zelfstandig:

* Nieuwe externe databronnen toevoegen.
* Productie-indexen wissen of vervangen.
* Gebruikersdata opnemen in testdatasets.
* Embeddingmodel of retrievalstrategie wijzigen zonder expliciete opdracht.

## Datasets en evaluaties

Bij datasets:

* Gebruik synthetische of geanonimiseerde data.
* Voeg geen echte persoonsgegevens toe.
* Voeg geen echte trainingsdata toe zonder expliciete toestemming.
* Documenteer wat de dataset test.
* Houd testcases klein en begrijpelijk.
* Voeg edge cases toe waar relevant.

Bij evaluaties:

* Beschrijf de evaluatiecriteria.
* Leg uit wat beter of slechter is geworden.
* Vergelijk waar mogelijk oude en nieuwe output.
* Voeg voorbeelden toe van geslaagde en mislukte output.
* Behandel evaluaties als kwaliteitsbewijs, niet als absolute waarheid.

## Security en privacy

Endurix kan gevoelige sportdata en persoonsgegevens verwerken.

Strikte regels:

* Geen echte persoonsgegevens in prompts, datasets of fixtures.
* Geen echte atleetdata in testbestanden.
* Geen tokens, API-keys of secrets in de repo.
* Geen logs met persoonlijke of medische informatie.
* Geen export van gebruikersdata naar externe services zonder expliciete opdracht.
* Geen AI-call die meer data verstuurt dan noodzakelijk.
* Geen trainingsadvies dat medische zekerheid suggereert.

Bij privacygevoelige wijzigingen:

* Markeer de PR als privacy-risk.
* Leg uit welke data wordt gebruikt.
* Leg uit waarom die data nodig is.
* Vraag menselijke review.

## Veiligheid van trainingsadvies

AI-output over training moet voorzichtig zijn.

Let extra op:

* Blessureklachten
* Ziekte
* Extreme vermoeidheid
* Onverklaarbare prestatieval
* Zeer hoge trainingsbelasting
* Te snelle opbouw
* Wedstrijdstress
* Voeding/hydratatie bij lange inspanning

AI mag in zulke gevallen geen harde medische conclusies trekken. De output moet voorzichtig formuleren en waar nodig adviseren om een coach of medisch professional te raadplegen.

## Outputformats

Gebruik vaste outputformats waar mogelijk.

Voor coachfeedback bijvoorbeeld:

* Samenvatting
* Positieve signalen
* Aandachtspunten
* Advies voor volgende stap
* Vragen aan de atleet
* Onzekerheden of ontbrekende data

Voor trainingsanalyse bijvoorbeeld:

* Belasting
* Intensiteit
* Herstel
* Consistentie
* Risico’s
* Advies
* Benodigde extra informatie

## Testing

Voor elke relevante AI/MLOps-wijziging:

* Draai bestaande evaluaties.
* Voeg testcases toe bij nieuwe promptfunctionaliteit.
* Controleer output op veiligheid.
* Controleer output op toon en bruikbaarheid.
* Controleer of privacyregels worden gevolgd.
* Vergelijk oude en nieuwe output waar mogelijk.
* Documenteer beperkingen.

Als er nog geen automatische evaluaties zijn:

* Voeg minimaal handmatige evaluatievoorbeelden toe.
* Beschrijf hoe de output gecontroleerd is.
* Maak een vervolgissue voor automatische evaluatie.

## Definition of Done

Een issue is pas klaar als:

* Doel van de wijziging duidelijk is.
* Prompt/RAG/evaluatie-wijziging is uitgelegd.
* Privacy-impact is gecontroleerd.
* Testdata is synthetisch of geanonimiseerd.
* Evaluatie of testbeschrijving is toegevoegd.
* Risico’s zijn benoemd.
* PR is gekoppeld aan Linear.
* Er is geen directe push naar `main`.

## Wat Codex wel mag doen

Codex mag:

* Promptteksten verbeteren binnen duidelijke scope.
* Evaluatiecases toevoegen.
* Synthetische testdata maken.
* Documentatie verbeteren.
* Kleine scripts aanpassen.
* Outputformats structureren.
* RAG-documentatie aanvullen.
* PR’s maken.

## Wat Codex niet zelfstandig mag doen

Codex mag niet zelfstandig:

* Naar `main` mergen.
* Echte gebruikersdata toevoegen.
* Secrets of API-keys toevoegen.
* Nieuwe AI-providers toevoegen.
* Embeddingmodellen wijzigen zonder expliciete opdracht.
* Productie-indexen wissen of vervangen.
* Medisch klinkend advies toevoegen.
* Privacyregels versoepelen.
* Grote promptarchitectuur wijzigen zonder review.
* Scope uitbreiden buiten het Linear issue.

## Review focus

Controleer bij reviews extra op:

* Onbedoeld gebruik van echte gebruikersdata.
* Te veel persoonsgegevens in prompts.
* Onveilige of te stellige trainingsadviezen.
* Ontbrekende evaluaties.
* Onduidelijke promptwijzigingen.
* Verouderde kennis in RAG-bronnen.
* Nieuwe externe afhankelijkheden.
* AI-output die coachbeoordeling vervangt in plaats van ondersteunt.
