flowchart TD
A[Malicious UI] --> B[Fake transaction preview]
B --> C[User trusts UI]
C --> D[Wallet signs real malicious data]
D --> E[Funds drained]

    F[Wallet Verification] -->|Prevents| D
