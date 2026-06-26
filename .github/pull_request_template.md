# Bestand 1: `.github/pull_request_template.md`

````md
## Linear issue

Closes END-

## Type wijziging

- [ ] Prompt
- [ ] Evaluatie
- [ ] RAG / knowledge base
- [ ] Dataset
- [ ] Script
- [ ] Documentatie
- [ ] Guardrail
- [ ] Experiment
- [ ] Tech debt
- [ ] Security/privacy

## Samenvatting

Beschrijf kort wat deze PR toevoegt of wijzigt.

## Gewijzigde onderdelen

- [ ] Prompt template
- [ ] Evaluatiecriteria
- [ ] Testdataset
- [ ] Synthetische data
- [ ] RAG-documentatie
- [ ] Knowledge base structuur
- [ ] Embedding/retrieval-configuratie
- [ ] Script
- [ ] Documentatie

## Waarom is deze wijziging nodig?

Beschrijf het probleem of de verbetering.

```text

````

## Acceptatiecriteria

Neem de acceptatiecriteria uit Linear over en vink af wat is opgelost.

* [ ]
* [ ]
* [ ]

## Evaluatie

Bij AI/MLOps-wijzigingen is een evaluatie of onderbouwde testbeschrijving verplicht.

* [ ] Bestaande evaluaties gedraaid
* [ ] Nieuwe evaluatiecases toegevoegd
* [ ] Oude en nieuwe output vergeleken
* [ ] Handmatige evaluatie toegevoegd
* [ ] Niet van toepassing, toelichting hieronder

Toelichting evaluatie:

```text
```

## Voorbeeldoutput

Gebruik waar mogelijk een voorbeeld van oude en nieuwe output.

### Oude output

```text
```

### Nieuwe output

```text
```

## Data-check

* [ ] Alleen synthetische data gebruikt
* [ ] Alleen geanonimiseerde data gebruikt
* [ ] Geen echte persoonsgegevens toegevoegd
* [ ] Geen echte atleetdata toegevoegd
* [ ] Geen echte trainingsbestanden toegevoegd
* [ ] Geen API-keys, tokens of secrets toegevoegd

Toelichting data:

```text
```

## Security / privacy check

* [ ] Geen secrets toegevoegd
* [ ] Geen persoonsgegevens in prompts
* [ ] Geen persoonsgegevens in datasets
* [ ] Geen echte sportdata in testbestanden
* [ ] Geen onnodige data richting AI-service
* [ ] Privacy-impact beschreven
* [ ] Menselijke review nodig bij privacy-impact

Toelichting security/privacy:

```text
```

## Veiligheid trainingsadvies

Controleer of AI-output niet te stellig of medisch klinkt.

* [ ] Geen medische diagnose
* [ ] Geen blessurediagnose
* [ ] Geen gevaarlijk trainingsadvies
* [ ] Onzekerheid wordt benoemd bij ontbrekende data
* [ ] Bij risico’s wordt coach/medisch professional genoemd waar passend
* [ ] AI ondersteunt coach/atleet, maar vervangt geen menselijke beoordeling

## RAG / knowledge base impact

* [ ] Geen RAG-impact
* [ ] Nieuwe bron toegevoegd
* [ ] Bron aangepast
* [ ] Bron verwijderd
* [ ] Retrieval-impact beschreven
* [ ] Bronbetrouwbaarheid gecontroleerd
* [ ] Geen auteursrechtelijk problematische content toegevoegd

Toelichting:

```text
```

## Testaanpak

* [ ] Python checks draaien succesvol
* [ ] Evaluaties draaien succesvol
* [ ] JSON/YAML-bestanden zijn valide
* [ ] Markdown gecontroleerd
* [ ] Handmatig getest
* [ ] Niet van toepassing, toelichting hieronder

Toelichting:

```text
```

## Risico’s voor reviewer

Waar moet extra op gelet worden?

```text
```

## Checklist voor merge

* [ ] PR is gekoppeld aan Linear
* [ ] PR is klein genoeg om goed te reviewen
* [ ] CI is groen
* [ ] Evaluatie of testbeschrijving is toegevoegd
* [ ] Privacy/data-check is ingevuld
* [ ] Er is geen directe push naar `main`

````