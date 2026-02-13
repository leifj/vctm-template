# Contributing to VCTM Credentials

This repository uses an automated workflow to generate Verifiable Credential Type Metadata (VCTM) files from markdown.

## Adding a New Credential

1. **Copy the template**: Start with `credentials/TEMPLATE.md` as a base
   ```bash
   cp credentials/TEMPLATE.md credentials/your-credential.md
   ```

2. **Edit the credential**:
   - Update the `vct` identifier in the front matter
   - Change the credential name and description
   - Define your claims following the format shown
   - Add or customize images if needed

3. **Add logo (optional)**:
   - Place image files in `credentials/images/`
   - Reference them in your markdown with `![Logo](images/your-logo.svg)`
   - The first image becomes the credential logo
   - SVG files are preferred and become SVG templates

4. **Test locally** (optional):
   - Install mtcvctm: `go install github.com/sirosfoundation/mtcvctm/cmd/mtcvctm@latest`
   - Generate VCTM: `mtcvctm generate credentials/your-credential.md`
   - Verify the output looks correct

5. **Commit and push**:
   ```bash
   git add credentials/your-credential.md
   git commit -m "Add your-credential VCTM"
   git push origin main
   ```

6. **Verify**: The GitHub Action will automatically generate VCTM files on the `vctm` branch

## Credential Markdown Format

### Front Matter (YAML)
```yaml
---
vct: https://example.com/credentials/unique-id  # Required: Unique identifier
background_color: "#1a365d"                     # Optional: Display color
text_color: "#ffffff"                           # Optional: Text color
extends: https://example.com/base-credential    # Optional: Base credential
---
```

### Claims Section
```markdown
## Claims

- `claim_name` (type): Description [flags]
```

**Supported types**: `string`, `date`, `number`, `boolean`, `object`, `array`

**Supported flags**:
- `[mandatory]` - Claim is required
- `[sd=always]` - Always use selective disclosure
- `[sd=never]` - Never use selective disclosure

### Examples

**Mandatory string claim**:
```markdown
- `given_name` (string): First name of the holder [mandatory]
```

**Optional date with selective disclosure**:
```markdown
- `birth_date` (date): Date of birth [sd=always]
```

**Simple optional claim**:
```markdown
- `email` (string): Email address
```

## Image Guidelines

- Use SVG format for logos when possible (scalable and becomes a template)
- Place all images in `credentials/images/` directory
- Keep file sizes reasonable (< 100KB recommended)
- Use descriptive filenames

## Best Practices

1. **Unique VCT identifiers**: Use your domain in the `vct` URL
2. **Clear descriptions**: Write concise, clear descriptions for each claim
3. **Appropriate types**: Use the correct type for each claim
4. **Selective disclosure**: Mark sensitive claims with `[sd=always]`
5. **Mandatory claims**: Only mark truly required claims as `[mandatory]`

## Questions?

Check the [mtcvctm documentation](https://github.com/sirosfoundation/mtcvctm) for more details.
