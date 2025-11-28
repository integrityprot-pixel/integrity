# integrity.txt — Minimal Public Integrity Protocol

integrity.txt is a simple, text-only file placed at the root of any website or project to declare public integrity commitments that are objectively verifiable by anyone. It is technology-neutral, organization-neutral, identity-neutral and fully open.

## Specification (v0.1)

The integrity.txt file must follow seven universal rules:

1. File Location
A plain UTF-8 text file named integrity.txt must exist at the root of the domain or project.

2. Format
The file must contain one declaration per line using the format: key: value

3. Verifiability
Every declaration must be objectively verifiable by any independent third party.

4. Proof of Integrity
The file must include a sha256: field containing the SHA-256 hash of the file itself.

5. No Tracking / No Cookies
Accessing integrity.txt must require no cookies, no JavaScript, no authentication and no redirects.

6. Updates
The file must be updated only when declarations materially change.

7. Public Accessibility
The integrity.txt file must remain publicly accessible at all times.

## Example integrity.txt file

integrity: public
tracking: none
cookies: none
data-use: minimal
ai-origin: declared
accessibility: open
sha256: (to be computed)

## How to Verify

Anyone can verify an integrity.txt file using any SHA-256 tool. The steps are universal:

1. Download the file from the root of the domain (for example: https://example.com/integrity.txt).
2. Compute the SHA-256 hash using any local or online tool.
3. Compare the computed value with the sha256: field published inside integrity.txt. They must match exactly.
4. Independently check each declaration:
   - tracking: none → visiting the site must not set any cookies or trackers
   - cookies: none → browser developer tools should show zero cookies
   - data-use: minimal → no unexpected forms, pop-ups, or collection patterns
   - ai-origin: declared → AI-generated content must be explicitly indicated
   - accessibility: open → the file must load without scripts, redirects, or accounts
5. If any declaration cannot be verified, the site is considered non-compliant.

## Optional Tools for SHA-256 Verification

You may use any independent tool you trust to compute or validate SHA-256 hashes. Examples include:

Local verification tools:
sha256sum (Linux, macOS), Get-FileHash (Windows)

Independent online verifiers:
https://www.virustotal.com/gui/file-analysis
https://emn178.github.io/online-tools/sha256_checksum.html
https://hash.expert

Automated public verifiers (optional):
https://api.timeproofs.io/api/verify?hash=<SHA256>

All methods must produce the same SHA-256 value published in the integrity.txt file.

## License

This protocol is released under the MIT License.
