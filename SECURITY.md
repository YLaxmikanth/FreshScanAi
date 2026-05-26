# Security Policy

## Supported Versions

Only the latest commit on `main` receives security fixes.

## Reporting a Vulnerability

**Do NOT open a GitHub issue, pull request, or discussion for a security vulnerability.** Public disclosure before a fix is in place puts every user of this project at risk.

### Private Disclosure

Report vulnerabilities by **email only**:

```
karanrathore23@zohomail.in
```

Subject line: `[SECURITY] FreshScan AI — <one-line summary>`

Include in your report:

1. **Description** — what the vulnerability is and which component is affected.
2. **Steps to reproduce** — exact, minimal steps that demonstrate the issue.
3. **Impact** — what an attacker could achieve by exploiting it.
4. **Affected versions/commits** — commit SHA or version string if known.
5. **Suggested fix** (optional) — if you have a patch or mitigation in mind.

Do not attach screenshots of credentials, keys, or personal data.

### Response Timeline

| Action | Target |
|--------|--------|
| Acknowledgement of receipt | Within **48 hours** |
| Initial triage / severity assessment | Within **5 days** |
| Fix or mitigation shipped | Within **14 days** for critical; **30 days** for others |
| Public disclosure | After the fix is merged and deployed |

### What Qualifies

Report issues such as:

- Authentication bypass or token leakage in the FastAPI auth layer (`auth.py`)
- Exposure of `SUPABASE_SERVICE_KEY` or other secrets through any code path
- SQL injection or insecure direct object reference in Supabase queries
- Arbitrary file upload or path traversal in the scan endpoints
- Cross-origin resource sharing (CORS) misconfiguration that exposes authenticated endpoints
- Any condition where `DEV_BYPASS_AUTH=true` or `DEV_MODE=true` is reachable in production

### What Does Not Qualify

- Bugs that affect only local development environments with `DEV_BYPASS_AUTH=true`
- Issues requiring physical access to the device
- Theoretical vulnerabilities with no demonstrated exploit path

### Coordinated Disclosure

We follow a **coordinated disclosure** model. Once a fix is in place:

1. A security advisory will be published in the GitHub Security tab.
2. The commit message will reference the CVE number if one has been assigned.
3. The reporter will be credited in the advisory unless they prefer anonymity.

---

Thank you for helping keep FreshScan AI and its users safe.
