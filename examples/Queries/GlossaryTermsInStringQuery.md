---
title: GlossaryTermsInStringQuery
---

# GlossaryTermsInStringQuery

## Query

```gql
query GlossaryTermsInStringQuery($string: String!) {
  glossaryTermsInString(string: $string) {
    substring
    term {
      id
      name
      definition
    }
  }
}
```

## Variables

```json
{
  "string": "Tree to 30 m high or spindly shrub; bark usually smooth (fissured at base of old trunks only), grey-green or dark grey to almost black; branchlets with waxy bloom, angular, slightly ribbed, minutely hairy. Leaves bipinnate, greyish-green; rachis 4–10 cm long, angular, pubescent, with a raised gland at the junction of each pinna pair; pinnae in 8–20 pairs; pinnules in 10–68 pairs, crowded, linear-oblong, 2–5 mm long, c. 0.5 mm wide, within a single pinna more or less equal in length, minutely pubescent, apex more or less acute. Inflorescence a raceme or panicle; heads globular, 25–35-flowered, bright yellow, peduncles c. 5 mm long. Pod straight or slightly curved, flattish, 5–9 cm long, 8–12 mm wide, slightly constricted, light brownish-purple, often with whitish bloom."
}
```