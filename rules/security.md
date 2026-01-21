# iOS Security

## Secrets (CRITICAL)
- Never hardcode API keys, tokens, or credentials.
- Use build configs, Keychain, or secure runtime provision.
- Do not commit certificates, provisioning profiles, or private keys.

## Networking
- ATS must stay enabled unless explicitly approved.
- Use HTTPS with TLS 1.2+.
- Validate hosts for sensitive endpoints.
- Avoid logging request/response bodies with PII.

## Data Storage
- Use Keychain for credentials and tokens.
- Avoid storing PII in `UserDefaults`.
- Encrypt sensitive local files and use `NSFileProtection`.
- Clear sensitive caches on logout and account deletion.

## Privacy
- Add required Info.plist usage strings with clear descriptions.
- Gate tracking behind explicit consent.
- Minimize data collection and retention.
- Avoid sending PII to analytics providers.

## App Store Policy
- Maintain accurate privacy disclosures.
- Validate export compliance and encryption declarations.
