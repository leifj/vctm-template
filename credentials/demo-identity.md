---
vct: https://example.com/credentials/demo-identity
background_color: "#1a365d"
text_color: "#ffffff"
---

# Demo Identity Credential

A demonstration verifiable credential for identity verification. This credential can be used as a template for creating your own VCTM credentials.

## Claims

- `given_name` "Given Name" (string): The given name of the credential holder [mandatory]
  - de-DE: "Vorname" - Der Vorname des Inhabers
  - fr: "Prénom" - Le prénom du titulaire
- `family_name` "Family Name" (string): The family name of the credential holder [mandatory]
  - de-DE: "Familienname" - Der Familienname des Inhabers
  - fr: "Nom de famille" - Le nom de famille du titulaire
- `birth_date` "Date of Birth" (date): Date of birth of the holder [sd=always]
  - de-DE: "Geburtsdatum" - Geburtsdatum des Inhabers
  - fr: "Date de naissance" - Date de naissance du titulaire
- `email` "Email" (string): Email address of the holder
- `nationality` "Nationality" (string): Nationality of the credential holder
  - de-DE: "Staatsangehörigkeit" - Staatsangehörigkeit des Inhabers
  - fr: "Nationalité" - Nationalité du titulaire
- `national_id` "National ID" (string): National identification number [sd=always]

## Images

![Logo](images/logo.svg)
