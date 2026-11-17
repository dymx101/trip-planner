# Coupang SSL/TLS Public Key Pinning (SPKI) Audit

A static audit dashboard comparing the TLS certificates and SPKI (Subject Public Key Information) SHA-256 pins for Coupang CDN and Streaming endpoints:
- `static.coupangcdn.com`
- `api.coupangstreaming.com`
- `discover.coupangstreaming.com`

## Summary Table

| Endpoint Domain | Dual-Cert (RSA + ECDSA) | RSA Leaf Pin (SHA-256) | ECDSA Leaf Pin (SHA-256) | Root CA |
|---|---|---|---|---|
| `static.coupangcdn.com` | ✅ Supported | `sha256/+Z25bV18x/xeQHzvCxyLTz+jYzUPCkfQbdjMdZ3ilK0=` | `sha256/KmV36vu7R6vPERV3BAynG4eEEaQ9cAFhgXMh+kcMCHI=` | DigiCert |
| `api.coupangstreaming.com` | ❌ RSA Only | `sha256/CzZ+zUcSiQQeESTfSlO0m1tG9+4aD1NZ/J7pwVMWzkU=` | Handshake Failed (Alert 40) | Sectigo / USERTrust |
| `discover.coupangstreaming.com` | ❌ RSA Only | `sha256/CzZ+zUcSiQQeESTfSlO0m1tG9+4aD1NZ/J7pwVMWzkU=` | Handshake Failed (Alert 40) | Sectigo / USERTrust |

## How to Test
```bash
# Node.js inspection script
node -e '...'
```
