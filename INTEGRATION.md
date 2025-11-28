# Integration Patch for integrity.txt

Projects may include the following block in their README to declare compliance with the integrity.txt protocol.

![integrity.txt](https://img.shields.io/badge/integrity.txt-active-blue)

This project implements the integrity.txt protocol, a minimal and verifiable transparency file placed at the root of the domain or repository.

To verify:

1. Download the integrity.txt file from the root of the domain or repo.
2. Compute its SHA-256 hash using any SHA-256 tool.
3. Compare it with the `sha256:` value inside the file.
4. Check that all declarations are objectively verifiable.

Accepted verification methods include:
- local commands (`sha256sum`, `Get-FileHash`)
- independent hash checkers (VirusTotal, emn178, hash.expert)
- automated public verifiers:
  https://api.timeproofs.io/api/verify?hash=<SHA256>
