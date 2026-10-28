# DevSecOps security pipeline

This repository demonstrates a practical, layered approach to application and infrastructure security. The goal is to catch issues early, reduce the chance of secret leakage, and provide a repeatable base for secure delivery.

## Control layers

1. Secret scanning
   - Detects credentials, tokens, and other high-risk strings before they reach the default branch.
   - Tooling: Gitleaks

2. Static code analysis
   - Reviews source code for risky patterns and unsafe practices.
   - Tooling: Semgrep

3. Dependency scanning
   - Inspects installed packages and lock files for known vulnerabilities.
   - Tooling: pip-audit, OSV-Scanner

4. IaC security review
   - Checks infrastructure as code against common misconfigurations.
   - Tooling: Checkov, Trivy

5. Kubernetes manifest review
   - Validates workload manifests for unsafe defaults and policy violations.
   - Tooling: Kubescape

6. SBOM generation
   - Produces a machine-readable inventory of the software being shipped.
   - Tooling: Anchore SBOM Action

## Repository usage

- Keep this repository as a reference implementation.
- Treat scan results as actionable engineering feedback, not a blanket blocker.
- Confirm findings before suppressing or ignoring them.
- Prefer small, targeted changes over broad exceptions.

## Remediation workflow

1. Review the failing job in GitHub Actions.
2. Identify whether the issue is a real leak, a dependency vulnerability, or a configuration risk.
3. Fix the root problem in source or configuration.
4. Re-run the relevant scan locally or in CI.
5. Only add an allowlist exception when it is justified and traceable.

## Notes

This repo intentionally avoids real secrets, credentials, or live cloud configuration. It is a sample baseline for portfolio use and secure engineering practices.
