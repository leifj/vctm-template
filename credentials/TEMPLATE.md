---
vct: https://example.com/credentials/your-credential-id
background_color: "#1a365d"
text_color: "#ffffff"
# doctype: com.example.credentials.your-credential
# namespace: com.example.credentials.your-credential
# w3c_type: YourCredentialType
---

# Your Credential Name

A brief description of what this credential represents and its purpose.

## Claims

- `claim_name` "Claim Label" (string): Description of this claim [mandatory]
  - de-DE: "Bezeichnung" - Beschreibung auf Deutsch
  - sv: "Etikett" - Beskrivning på svenska
- `another_claim` "Another Claim" (type): Description of another claim
- `optional_claim` "Optional Claim" (string): An optional claim
- `selective_claim` "Selective Claim" (string): A claim with selective disclosure [sd=always]

### Claim Types

Available types for claims:
- `string` - Text values (default)
- `integer` - Whole numbers  
- `date` - Date values (YYYY-MM-DD)
- `datetime` - Date with time (ISO 8601)
- `boolean` - True/false values
- `image` - Base64-encoded image data

## Images

![Logo](images/logo.svg)
