---
vct: https://example.com/credentials/student-id
background_color: "#0047AB"
text_color: "#ffffff"
---

# Student ID Credential

A verifiable credential representing a student identification card. This credential demonstrates SVG template rendering with claim placeholders.

## Claims

- `given_name` (string): Student's given name [mandatory, svg_id=given_name]
- `family_name` (string): Student's family name [mandatory, svg_id=family_name]
- `student_id` (string): Unique student identification number [mandatory, svg_id=student_id]
- `institution` (string): Name of the educational institution [mandatory, svg_id=institution]
- `program` (string): Academic program or major [svg_id=program]
- `valid_from` (date): Start date of validity [mandatory]
- `valid_until` (date): Expiration date of the credential [mandatory, svg_id=valid_until]
- `photo` (image): Student photo [sd=always]

## Images

![Student ID Template](images/student-id-template.svg)
