This project follows the integrity.txt protocol
[![](https://img.shields.io/badge/integrity.txt-enabled-2b8a3e)]()

# integrity.txt — Minimal Public Integrity Protocol

integrity.txt is a simple, text-only file placed at the root of any website or project to declare public integrity commitments that are objectively verifiable by anyone. It is technology-neutral, organization-neutral, identity-neutral, and fully open.

## Specification (v0.1)

The integrity.txt file must follow seven universal rules defined by the protocol:

### 1. File Location
A plain UTF-8 text file named integrity.txt must exist at the root of the domain or project. It must be accessible without cookies, without JavaScript, without authentication, and without redirects, and must use one line per declaration in the format key: value.

### 2. Tracking Declaration
The file must declare the presence or absence of tracking technologies (for example: tracking: none, limited, or analytics-only).

### 3. Cookies Declaration
The file must declare whether the site sets cookies and for what purpose (for example: cookies: none, functional-only, analytics, or advertising).

### 4. Data-Use and Logging
The file must declare how user data or logs are handled in a verifiable manner (for example: data-use: minimal, logs: anonymized, or retention: 30d).

### 5. Third-Party Services
The file must declare any third-party services involved that may receive user data (for example: third-parties: none, cloudflare, plausible).

### 6. Accessibility and Openness
The file must declare accessibility and public availability commitments (for example: accessibility: open, availability: always-on).

### 7. Proof of Integrity
The file must include a line using the sha256: key containing the SHA-256 hash of the file itself.  
Example: sha256: <sha256_value>

## Example integrity.txt file

tracking: none  
cookies: none  
data-use: minimal  
third-parties: none  
accessibility: open  
sha256: (SHA-256 of this file)

## How to Verify

Anyone can verify an integrity.txt file using any SHA-256 tool. The steps are universal:
1. Download the file from the root of the domain.  
2. Compute its SHA-256 hash using any local or online tool.  
3. Compare the computed value with the sha256: field. They must match exactly.  
4. Independently check each declaration (tracking, cookies, data-use, third-parties, accessibility) through inspection or developer tools.  
5. If any declaration cannot be verified, the site is non-compliant.

## Optional Tools for SHA-256 Verification

Local tools: sha256sum, shasum -a 256, Get-FileHash  
Online tools: https://emn178.github.io/online-tools/sha256_checksum.html, https://hash.expert, https://www.virustotal.com/gui/file-analysis  
Automated verification (optional): https://api.timeproofs.io/api/verify?hash=<SHA256>

## Related Protocols

The integrity.txt protocol can be used alongside other independent, root-level public transparency standards:

- authenticity.txt — declarations of human/AI origin  
- rights.txt — declarations of usage rights and permissions  
- explainable-ia.txt — declarations of AI explainability and model transparency

These standards are independent and can be implemented separately or together.

## License

This protocol is released under the MIT License.
