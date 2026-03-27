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

## Delegation-Ready Checklist
- Define top 3 partner use-cases and required proofs of attendance.
- Choose custody approach (in-house ledger vs. third-party escrow API) and settlement rails.
- Specify policy templates (stakes, time windows, auto-release/forfeit logic).
- Stand up API gateway + workflow service skeleton; emit domain events to bus.
- Integrate at least one proof-of-attendance mechanism end-to-end.
- Wire observability (metrics/traces/logs) and basic KYC + fraud signals.
- Ship partner docs: auth, endpoints, webhooks, sandbox credentials.
