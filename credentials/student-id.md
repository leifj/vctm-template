---
vct: https://example.com/credentials/student-id
background_color: "#0047AB"
text_color: "#ffffff"
doctype: com.example.credentials.student-id
---

# Student ID Credential

A verifiable credential representing a student identification card. This credential demonstrates SVG template rendering with claim placeholders and multi-language support.

## Claims

- `given_name` "Given Name" (string): Student's given name [mandatory, svg_id=given_name]
  - de-DE: "Vorname" - Der Vorname des Studierenden
  - sv: "Förnamn" - Studentens förnamn
- `family_name` "Family Name" (string): Student's family name [mandatory, svg_id=family_name]
  - de-DE: "Familienname" - Der Familienname des Studierenden
  - sv: "Efternamn" - Studentens efternamn
- `student_id` "Student ID" (string): Unique student identification number [mandatory, svg_id=student_id]
  - de-DE: "Matrikelnummer" - Die eindeutige Matrikelnummer
  - sv: "Studentnummer" - Unikt studentnummer
- `institution` "Institution" (string): Name of the educational institution [mandatory, svg_id=institution]
  - de-DE: "Bildungseinrichtung" - Name der Bildungseinrichtung
  - sv: "Utbildningsinstitution" - Namn på utbildningsinstitutionen
- `program` "Academic Program" (string): Academic program or major [svg_id=program]
  - de-DE: "Studiengang" - Studiengang oder Hauptfach
  - sv: "Program" - Akademiskt program eller huvudämne
- `valid_from` "Valid From" (date): Start date of validity [mandatory]
- `valid_until` "Valid Until" (date): Expiration date of the credential [mandatory, svg_id=valid_until]
- `photo` "Photo" (image): Student photo [sd=always]

## Images

![Student ID Template](images/student-id-template.svg)
