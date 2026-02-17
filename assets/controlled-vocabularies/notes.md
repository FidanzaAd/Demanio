# Vocabolari Controllati

I vocabolari controllati sono pubblicati in formato RDF/Turtle (media type text/turtle) e l'estensione del file è `.ttl`.

I file CSV e JSON sono generati automaticamente a partire dai file TTL usando 
lo script `scripts/create_csv_json.py`.

## Struttura Directory

Ogni vocabolario controllato deve seguire questa struttura:

```
nome-vocabolario/
├── latest/
│   ├── nome_vocabolario.ttl   # Sorgente RDF/Turtle
│   ├── nome_vocabolario.csv   # Generato automaticamente
│   └── nome_vocabolario.json  # Generato automaticamente
└── v{version}/
    ├── nome_vocabolario.ttl
    ├── nome_vocabolario.csv
    └── nome_vocabolario.json
```

## Generazione CSV/JSON

Per generare i file CSV e JSON da un vocabolario:

```bash
python scripts/create_csv_json.py assets/controlled-vocabularies/nome-vocabolario/latest/nome_vocabolario.ttl
```

## Standard Utilizzati

- **RDF/Turtle**: https://www.w3.org/TR/turtle/
- **SKOS**: https://www.w3.org/TR/skos-reference/
- **JSON-LD**: https://www.w3.org/TR/json-ld11/
