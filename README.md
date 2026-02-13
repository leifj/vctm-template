# VCTM Template Repository

A template repository for maintaining Verifiable Credential Type Metadata (VCTM) credentials as markdown files. This template uses the [sirosfoundation/mtcvctm](https://github.com/sirosfoundation/mtcvctm) GitHub Action to automatically generate VCTM files from markdown.

## Quick Start

1. **Use this template**: Click "Use this template" to create your own repository
2. **Add credentials**: Create markdown files in the `credentials/` directory
3. **Push to main**: The GitHub Action will automatically generate VCTM files on the `vctm` branch

## Structure

```
.
├── credentials/              # Markdown credential definitions
│   ├── demo-identity.md     # Example credential
│   └── images/              # Logo and image assets
│       └── logo.svg         # Generic credential logo
├── .github/
│   └── workflows/
│       └── vctm.yml         # GitHub Action workflow
└── README.md
```

## Creating Credentials

Create markdown files in the `credentials/` directory with the following format:

```markdown
---
vct: https://example.com/credentials/your-credential
background_color: "#1a365d"
text_color: "#ffffff"
---

# Your Credential Name

A description of your credential.

## Claims

- `claim_name` (string): Description of the claim [mandatory]
- `optional_claim` (string): Optional claim
- `selective_disclosure_claim` (date): Claim with selective disclosure [sd=always]

## Images

![Logo](images/logo.svg)
```

### Front Matter Options

- `vct`: Verifiable Credential Type identifier (required)
- `background_color`: Background color for credential display
- `text_color`: Text color for credential display
- `extends`: Comma-separated list of VCT identifiers this type extends

### Claim Format

```
- `claim_name` (type): Description [mandatory] [sd=always|never]
```

- **claim_name**: The claim identifier
- **type**: Value type - `string`, `date`, `number`, etc. (default: `string`)
- **[mandatory]**: Mark the claim as required
- **[sd=always|never]**: Selective disclosure setting

## How It Works

1. When you push changes to markdown files in `credentials/`, the GitHub Action triggers
2. The `sirosfoundation/mtcvctm` action processes all markdown files
3. VCTM JSON files are generated and committed to the `vctm` branch
4. A registry file is created at `.well-known/vctm-registry.json`

## Accessing Generated Files

After the action runs, your VCTM files will be available on the `vctm` branch:

```
https://github.com/YOUR-USERNAME/YOUR-REPO/raw/vctm/demo-identity.vctm
```

## Customization

### Change the base URL

Edit `.github/workflows/vctm.yml` and update the `base-url` parameter:

```yaml
base-url: https://your-domain.com/credentials
```

### Change the output branch

Edit `.github/workflows/vctm.yml` and update the `vctm-branch` parameter:

```yaml
vctm-branch: your-branch-name
```

## License

This template is available as open source under the terms of your chosen license.

## Resources

- [mtcvctm GitHub Repository](https://github.com/sirosfoundation/mtcvctm)
- [VCTM Specification](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-sd-jwt-vc-11#section-6)
- [Siros Foundation Documentation](https://sirosfoundation.github.io/docs/)
