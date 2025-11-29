This project follows the integrity.txt protocol  
[![](https://img.shields.io/badge/integrity.txt-enabled-2b8a3e)]()

# integrity.txt — Minimal Public Integrity Protocol

**integrity.txt** is a simple, text-only file placed at the root of any website or project to declare public integrity commitments that are objectively verifiable by anyone.  
It is technology-neutral, organization-neutral, identity-neutral, and fully open.

---

## Specification (v0.1)

The integrity.txt file must follow the seven universal rules defined by the protocol:

### 1. File Location  
A plain UTF-8 text file named **integrity.txt** must exist at the root of the domain or project.

### 2. Format  
The file must contain one declaration per line using the format:  
`key: value`

### 3. Verifiability  
Every declaration must be objectively verifiable by any independent third party.

### 4. Proof of Integrity  
The file must include a line using the **hash:** key containing the SHA-256 hash of the file itself.  
Example:  
`hash: <sha256_value>`

### 5. No Tracking / No Cookies  
Accessing integrity.txt must require no cookies, no JavaScript, no authentication, and no redirects.

### 6. Updates  
The file must be updated only when declarations materially change.

### 7. Public Accessibility  
The integrity.txt file must remain publicly accessible at all times without friction.

---

## Example integrity.txt file

```
integrity: public
tracking: none
cookies: none
data-use: minimal
ai-origin: declared
accessibility: open
hash: (SHA-256 of this file)
```

---

## How to Verify

Anyone can verify an integrity.txt file using any SHA-256 tool.  
The steps are universal:

1. Download the file from the root of the domain  
   (example: `https://example.com/integrity.txt`)

2. Compute its SHA-256 hash using any local or online tool.

3. Compare the computed hash with the `hash:` field inside integrity.txt.  
   They must match **exactly**.

4. Independently check each declaration:  
   - `tracking: none` → visiting the site must not trigger trackers  
   - `cookies: none` → devtools must show zero cookies  
   - `data-use: minimal` → no unnecessary collection  
   - `ai-origin: declared` → AI-generated content must be marked  
   - `accessibility: open` → file must load without JS, redirects, or authentication

5. If any declaration cannot be verified, the site is **non-compliant**.

---

## Optional Tools for SHA-256 Verification

Any independent and trusted tool may be used to compute or validate SHA-256 hashes.

### Local tools
- `sha256sum` (Linux, macOS)  
- `shasum -a 256` (macOS)  
- `Get-FileHash` (Windows PowerShell)

### Independent online verifiers
- https://emn178.github.io/online-tools/sha256_checksum.html
- https://hash.expert
- https://www.virustotal.com/gui/file-analysis

### Automated public verifiers (optional)
TimeProofs can verify existence and timestamp of a hash:  
`https://api.timeproofs.io/api/verify?hash=<SHA256>`

All methods must yield the same SHA-256 value published inside the integrity.txt file.

---

## License

This protocol is released under the MIT License.
