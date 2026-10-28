# DevSecOps Security Scanning

A practical portfolio repository for secure software delivery, infrastructure review, and engineering guardrails.

## Scope

- Secret scanning and policy enforcement
- Static application security testing (SAST)
- Dependency vulnerability scanning
- Infrastructure-as-code review
- Kubernetes manifest validation
- SBOM generation and security reporting

## Purpose

This repository demonstrates a layered DevSecOps baseline that teams can adapt for Azure, cloud-native, and application delivery workflows. It focuses on early detection and clear remediation guidance instead of reactive firefighting.

## Included assets

- GitHub Actions workflow for security checks
- Gitleaks configuration for secret detection
- Trivy ignore baseline
- Example Kubernetes deployment manifest
- Security pipeline documentation

## Security workflow summary

The repository includes a multi-stage pipeline that checks for:

- leaked credentials and tokens
- risky application patterns
- vulnerable dependencies
- infrastructure misconfigurations
- unsafe Kubernetes manifests
- incomplete software inventory

For implementation details and usage guidance, see [docs/devsecops-pipeline.md](docs/devsecops-pipeline.md).
