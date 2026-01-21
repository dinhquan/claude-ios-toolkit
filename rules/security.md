# iOS Security

## Secrets (CRITICAL)
- Never hardcode API keys or tokens
- Use build configs or Keychain

## Networking
- ATS must stay enabled unless approved
- Use HTTPS with TLS 1.2+
- Validate certificates when required

## Data Storage
- Use Keychain for credentials
- Avoid storing PII in UserDefaults
- Encrypt sensitive local files

## Privacy
- Add required Info.plist usage strings
- Gate tracking behind consent
- Avoid logging PII
