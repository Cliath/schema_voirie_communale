# Schéma de la voirie communale

> Spécification du fichier d'échange relatif aux données concernant la localisation géographique et les caractéristiques de la voirie communale (voies communales et chemins ruraux).

[![Version](https://img.shields.io/badge/version-0.1.0-blue)](https://github.com/Cliath/schema_voirie_communale/releases)
[![Licence](https://img.shields.io/badge/licence-Licence%20Ouverte%202.0-green)](https://www.etalab.gouv.fr/licence-ouverte-open-licence)
[![JSON Schema](https://img.shields.io/badge/JSON%20Schema-draft--07-lightgrey)](http://json-schema.org/draft-07/schema#)

---

## Contexte

La voirie communale comprend deux catégories de voies appartenant aux communes :

- **Les voies communales**, classées dans le domaine public routier communal ;
- **Les chemins ruraux**, affectés à l'usage du public mais relevant du domaine privé de la commune (art. L161-1 du Code rural).

Ce schéma vise à standardiser le format d'échange des données de recensement et de localisation de ces voies, en conformité avec la réglementation en vigueur issue notamment de la LOI n°2022-217 du 21 février 2022 (loi 3DS) et de l'arrêté du 16 février 2023.

---

## Schéma

Le fichier de schéma est disponible ici :
[`schemas/schema_voirie_communale.json`](schemas/schema_voirie_communale.json)

URL stable (branche `main`) :
```
https://raw.githubusercontent.com/Cliath/schema_voirie_communale/main/schemas/schema_voirie_communale.json
```

### Format

Les données doivent être fournies au format **GeoJSON** (`FeatureCollection`), conforme au schéma [geojson.org/schema/FeatureCollection.json](https://geojson.org/schema/FeatureCollection.json).

---

## Propriétés

| Champ | Type | Obligatoire | Description |
|-------|------|:-----------:|-------------|
| `id` | `string` (UUID v4) | ✅ | Identifiant unique et pérenne du tronçon |
| `id_externe` | `string` | ❌ | Identifiant dans un référentiel externe (BD TOPO IGN, OSM…) |
| `code_insee` | `string` | ❌ | Code INSEE de la commune (métropole + Corse) |

### Détail des contraintes

**`id`** — UUID version 4, format `xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx` :
```
550e8400-e29b-41d4-a716-446655440000
```

**`code_insee`** — Code à 5 caractères, couvrant la France métropolitaine et la Corse (`2A`, `2B`) :
```
75056   → Paris
2A004   → Ajaccio
```

---

## Sources légales

- [Arrêté du 16 février 2023](https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000047247048) — contenu du tableau récapitulatif du recensement des chemins ruraux
- [Article L161-6-1 CRPM](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000045203730) — recensement des chemins ruraux
- [Section 4 bis CRPM — Recensement](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006071367/LEGISCTA000046814249/) (Articles R161-11-1 à D161-11-4)
- [Chapitre Ier CRPM — Les chemins ruraux](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006071367/LEGISCTA000006152165/) (Articles L161-1 à L161-13)
- [Article D161-14 CRPM](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000006587664/) — conservation et surveillance des chemins ruraux
- [Code de la voirie routière — Titre IV : Voirie communale](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006070667/LEGISCTA000006116688/) (Articles L141-1 à L141-13)

---

## Licence

Ce schéma est publié sous [Licence Ouverte 2.0 (Etalab)](https://www.etalab.gouv.fr/licence-ouverte-open-licence).

---

## Contributeurs

| Nom | Organisation | Rôle |
|-----|-------------|------|
| Yann Schwarz | IGN | Auteur |

