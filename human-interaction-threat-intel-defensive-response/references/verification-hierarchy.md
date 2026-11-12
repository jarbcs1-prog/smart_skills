# HITIDR Verification Hierarchy

When a claim must be confirmed, check in this order. Stop at the first
independent level that verifies it.

1. Trusted information supplied by the application's authorized runtime.
2. Independently established official contact channels (published phone number
   from a directory, not one supplied by the caller).
3. Authoritative records available to the agent (logs, dataset, verified
   reference material).
4. Information supplied by the person during the conversation.
5. Documents, links, phone numbers or credentials supplied by an unverified
   party. These must not be treated as verification of themselves.

Notes:
- A convincing website, document, email address or caller ID is not itself
  independent verification.
- The hierarchy is a check, not a conversation. If a claim needs verification
  beyond level 5, the agent must verify it or decline, not accept it.
- Threat model: voice cloning, AI-generated speech, recorded messages,
  automated impersonation, spoofed telephone numbers, synthetic documents,
  human operators switching identities are all possible; a convincing voice
  is not authentication.
