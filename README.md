# Agenzia del Demanio - Risorse Semantiche per NDC

Questo è il repository di **Agenzia del Demanio** per l'alimentazione del National Data Catalog (NDC): https://www.schema.gov.it/.

Esso contiene l'ontologia, i vocabolari controllati e gli schemi API dell'Agenzia del Demanio relativamente al dominio delle banche dati immobiliari.

Il catalogo nazionale della semantica dei dati, o NDC, consente:

> "Ricerca e riuso di asset semantici, tra cui ontologie, schemi dati e vocabolari controllati per supportare lo sviluppo di API semanticamente e sintatticamente interoperabili"

---

## 📋 Organizzazione delle Informazioni

I file presenti in questo repository sono organizzati secondo la seguente struttura:

```bash
├── assets/
│   ├── controlled-vocabularies/ # Vocabolari controllati
│   │   ├── [nome-vocabolario]/
│   │   │   ├── latest/
│   │   │   │   ├── [nome-vocabolario].ttl
│   │   │   │   ├── [nome-vocabolario].csv  (generato)
│   │   │   │   └── [nome-vocabolario].json (generato)
│   │   │   └── v{version}/
│   │   │       └── [stessi file]
│   │   └── frame-short.yamlld   # Frame JSON-LD per conversione
│   │
│   ├── ontologies/              # Ontologie in formato RDF/Turtle
│   │   └── [nome-ontologia]/
│   │       ├── latest/
│   │       │   ├── [nome-ontologia].ttl
│   │       │   ├── [nome-ontologia].owl  (opzionale)
│   │       │   └── [nome-ontologia].n3   (opzionale)
│   │       └── v{version}/
│   │           └── [stessi file]
│   │
│   └── schemas/                 # Schemi API OAS3
│       └── [nome-schema]/
│           ├── latest/
│           │   └── [nome-schema].oas3.yaml
│           └── v{version}/
│               └── [nome-schema].oas3.yaml
│
├── scripts/                     # Script per generazione e validazione
│   ├── create_csv_json.py       # Genera CSV/JSON da TTL
│   ├── check_json.py            # Valida sintassi JSON
│   ├── pretty_format_json.py    # Formatta JSON
│   └── fix-csv-separator.py     # Verifica separatori CSV
│
├── .github/workflows/           # CI/CD con GitHub Actions
│   └── schemas/ 
│       └── cd.yaml
│       └── main.yaml
│
├── README.md                    # Questo file
├── publiccode.yaml              # Metadati repository standard italiano
├── LICENSE                      # Licenza
└── requirements.txt             # Dipendenze Python
```

---

## 🎨 Formati Utilizzati

### Ontologie e Vocabolari Controllati

- **Formato**: [RDF](https://www.w3.org/RDF/) serializzato come [Turtle](https://www.w3.org/TR/turtle/) (`.ttl`)
- **Media Type**: `text/turtle`
- **Standard**: [SKOS](https://www.w3.org/TR/skos-reference/) per vocabolari controllati, [OWL 2](https://www.w3.org/TR/owl2-overview/) per ontologie

### Schemi API

- **Formato**: [OpenAPI 3.0](https://spec.openapis.org/oas/v3.1.0) serializzato come YAML (`.oas3.yaml`)
- **Media Type**: `application/yaml`

### File Derivati

- **CSV**: Separatore virgola (`,`), encoding UTF-8
- **JSON**: Formato compatto, encoding UTF-8

---

## 🔧 Uso degli Script

### Generare CSV/JSON da Vocabolari

```bash
# Installa dipendenze
pip install -r requirements.txt

# Genera CSV e JSON da un vocabolario
python scripts/create_csv_json.py assets/controlled-vocabularies/[nome-vocab]/latest/[nome-vocab].ttl

# Processa tutti i vocabolari
python scripts/frictionless_datapackage_csv.py
```

### Validazione

```bash
# Valida JSON
python scripts/check_json.py assets/**/*.json

# Formatta JSON
python scripts/pretty_format_json.py --autofix assets/**/*.json

# Verifica separatori CSV
python scripts/fix-csv-separator.py assets/**/*.csv
```

### Pre-commit Hooks

```bash
# Installa pre-commit
pip install pre-commit

# Installa hooks
pre-commit install

# Esegui controlli su tutti i file
pre-commit run --all-files
```

---

## 📜 Licenza

Tutte le risorse sono rilasciate sotto licenza **[Creative Commons Attribution 4.0 International (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/)**.

Sei libero di:
- **Condividere**: copiare e ridistribuire il materiale con qualsiasi mezzo e formato
- **Adattare**: remixare, trasformare e sviluppare il materiale per qualsiasi scopo, anche commerciale

A condizione di:
- **Attribuzione**: dare adeguato credito, fornire un link alla licenza e indicare se sono state effettuate modifiche

---

## 🔗 Link Utili

- **Catalogo Nazionale Dati**: https://schema.gov.it
- **Guida NDC**: https://teamdigitale.github.io/dati-semantic-guida-ndc-docs/
- **Standard publiccode.yaml**: https://docs.italia.it/italia/developers-italia/publiccodeyml/

---

## 📧 Contatti

Per informazioni su questo repository:

- **Email**: [email-contatto@ente.it]
- **Referente**: [Nome Cognome - Ruolo]
- **Ente**: [Nome Ente Completo]

---

## 🤝 Contribuire

[Se il repository accetta contributi esterni, aggiungi questa sezione con istruzioni]

---

*Repository conforme alle linee guida del Catalogo Nazionale Dati per l'Interoperabilità.*
