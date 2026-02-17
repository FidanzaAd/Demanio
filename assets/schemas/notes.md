# Schemi Dati

Gli schemi dati sono pubblicati in formato OpenAPI Specifications versione 3 (OAS3).

I file sono serializzati in formato YAML e l'estensione è `.oas3.yaml`.

## Struttura Directory

Ogni schema deve seguire questa struttura:

```
nome-schema/
├── latest/
│   └── nome-schema.oas3.yaml   # Schema OpenAPI 3
└── v{version}/
    └── nome-schema.oas3.yaml
```

## Convenzioni

- File YAML valido secondo OpenAPI 3.0 specification
- Includere sezione `info` con title, version, description
- Documentare tutti gli endpoint e schemi dati
- Fornire esempi quando possibile

## Validazione

Per validare gli schemi OAS3, usa tool come:
- Swagger Editor: https://editor.swagger.io/
- Redoc: https://github.com/Redocly/redoc

## Standard Utilizzato

- **OpenAPI 3.0**: https://spec.openapis.org/oas/v3.1.0
