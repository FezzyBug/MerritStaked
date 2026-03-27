# MerritStaked

## Reframed Product
**Commitment-as-a-Service API** that lets partners (e.g., dating apps, matchmakers) hold deposits, verify attendance, and resolve outcomes through a distributed backend layer.

## System Architecture (Infra-Level)
- **API Gateway**: Single entrypoint (REST/GraphQL) with auth, rate limits, audit logging.

- **Orchestration Layer**: Workflow engine (state machine) for pledges -> attendance -> resolution.

- **Funds & Escrow Ledger**: Custody accounts, ledgered transfers, release rules, dispute holds.

- **Identity & Verification**: KYC/phone/email, proof-of-attendance adapters (QR/NFC, GPS, host attestations).
- **Policy Engine**: Configurable rules per partner (stakes, deadlines, acceptable proofs, auto-refunds).

- **Event Bus**: Emits domain events (PledgeCreated, AttendanceVerified, ForfeitResolved) to partners/webhooks.
- **Observability & Trust**: Metrics, traces, tamper-evident logs for compliance-grade audit.