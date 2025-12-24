flowchart LR
    A[Transaction Params] --> B[Safe Hash Calculator]
    B --> C[Generated Hash]
    C --> D[Compare with Hardware Wallet]
    D -->|Match| E[Safe to Sign]
    D -->|Mismatch| F[Reject Transaction]
