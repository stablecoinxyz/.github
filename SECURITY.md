# SBC Security Policy

SBC builds money-moving software, including a fiat-backed stablecoin, cross-chain intent settlement, peg-defense systems, account-abstraction infrastructure, and the x402 agent-payment stack. We take security reports seriously and investigate them promptly.

This policy covers vulnerabilities in deployed SBC systems and in code contained in the public repositories under [github.com/stablecoinxyz](https://github.com/stablecoinxyz).

## Reporting a vulnerability

Please email [security@stablecoin.xyz](mailto:security@stablecoin.xyz) rather than opening a public issue for anything that could affect confidentiality, integrity, availability, or the movement of funds.

Please include, where available:

- A clear description of the issue and steps to reproduce it.
- The affected repository, package, service, contract, or program.
- The relevant network, contract address, transaction, or deployment.
- A proof of concept and whether it was tested on testnet, mainnet, or locally.
- The impact you believe an attacker could achieve.
- Any relevant severity assessment or bounty request.

Please use testnet or a local reproduction whenever possible. Do not include secrets, private keys, or unnecessary personal data in your report.

We aim to acknowledge reports within 2 business days and provide an initial triage assessment within 5 business days. If you do not receive an acknowledgment, please resend the report with `URGENT SECURITY REPORT` in the subject line.

## In scope

Examples of in-scope issues include:

- Live SBC smart contracts, Solana programs, and settlement or attestation paths.
- Unauthorized movement or minting of funds.
- Bypasses of authorization, quorum, signature, replay, accounting, or settlement controls.
- Account-abstraction infrastructure, including paymasters and bundlers.
- SBC SDKs, packages, APIs, and the x402 facilitator.
- Security issues in SBC demo applications that could reasonably be copied into a production integration.
- Exposure of SBC signing keys, credentials, or sensitive deployment configuration.

## Generally out of scope

The following are generally out of scope or may receive lower priority:

- Vulnerabilities solely in third-party infrastructure or dependencies. Please report those to the relevant maintainer as well. Unsafe SBC integration, configuration, validation, or use of a third-party component remains in scope.
- Behaviors that are documented and operate as intended, such as a paymaster sponsoring user operations according to its stated design.
- Issues that are already publicly disclosed, although we may still assess their effect on live SBC systems.
- Findings that depend on assumptions or attacker capabilities not reasonably available in the affected deployment.
- Reports without enough information to reproduce or assess the issue after we have requested clarification.
- Purely theoretical concerns without a concrete security impact.
- Reports based only on generic scanner output, automated tool output, or speculative claims without validation.
- Reports that identify multiple symptoms of the same underlying issue without demonstrating additional impact.

Please report uncertain findings anyway. We would rather assess a low-impact or informational report than miss a real issue.

## Triage and bounty eligibility

We assess each report on its technical merits, practical impact, exploitability, and quality of evidence. A report’s severity label, CVSS score, bounty request, or number of claimed attack scenarios does not determine our assessment.

We may reject, close, or classify a report as informational, by design, duplicate, not reproducible, or otherwise ineligible where it:

- Does not demonstrate a plausible security impact.
- Relies on unrealistic assumptions or unattainable attacker capabilities.
- Repackages the same underlying issue as multiple separate findings without materially different impact.
- Uses exaggerated, speculative, or unsupported severity claims.
- Provides only low-effort, generic, or automated output without meaningful validation.
- Describes expected behavior or a documented product decision.
- Requires an attack path that is not available in the affected deployment.

We reserve the right to determine whether a report qualifies for a bounty, the appropriate bounty amount, and whether any bounty will be paid. Acceptance of a report, acknowledgment of a vulnerability, remediation of an issue, publication of a fix, or attribution to a reporter does not create an obligation to pay a bounty.

In particular, **we may accept, investigate, remediate, or publicly credit a report without paying a bounty**. A bounty may be withheld where the report is low effort, duplicates a known issue, materially overstates impact, combines multiple claims without demonstrating separate impact, or otherwise does not meet our standards for bounty eligibility.

Where multiple reports concern the same underlying root cause, we may treat them as a single finding and award any bounty only to the first qualifying report, subject to our discretion. We may also decline to pay a bounty where the report’s primary value is confirmation of an issue already known to SBC.

We do not guarantee that every valid security report will receive a monetary reward. Bounties are discretionary and may depend on novelty, evidence quality, exploitability, impact, responsible disclosure, and the practical value of the report to SBC.

## Bounty payment and identity verification

What we ask for depends on what you want.

- **Credit only.** Nothing. Choose a handle, or ask to stay unnamed.
- **A small award.** A name, a country of residence, and a destination address or account. We screen recipients against the sanctions lists administered by the U.S. Treasury’s Office of Foreign Assets Control, and those rules carry no minimum amount. We do not ask for identity documents or tax forms at this level.
- **A larger award.** Where U.S. tax reporting applies, currently where payments to one person reach $2,000 in a calendar year, we also need a completed Form W-9 or Form W-8BEN, and we may ask you to complete an identity verification check. That threshold is an annual total, so several smaller awards to the same researcher can reach it.

Awards may be paid in SBC. You are responsible for any taxes owed on an award.

In every case we cannot pay a recipient we are unable to screen, which means we cannot pay a fully anonymous or pseudonymous recipient. We also cannot pay where screening or verification fails, or where payment would be prohibited by applicable law. This is a compliance requirement, not a judgment about the quality of the report.

Anonymity is always your choice, and it does not change how we handle the report. An anonymous report is triaged, investigated, and remediated on the same terms as any other. We will still recognize the work, with credit in a security fix note or coordinated disclosure under a handle, or with no name at all if you prefer. Remaining anonymous forfeits only the monetary payment.

## Our commitments

- We do not silently discard reports. Each report receives a documented disposition, such as confirmed, partially valid, informational, duplicate, by design, not reproducible, or needs more information.
- A human reviews high-impact severity decisions and proposed fixes.
- Reports involving active exploitation, exposed signing keys, unauthorized movement or minting of funds, settlement or attestation bypass, contract-admin compromise, or critical disruption receive the highest priority.
- We will not describe a finding as fixed until the fix is deployed and its behavior is verified against the affected live system where feasible.
- We will provide status updates when an investigation or remediation requires more time.

## Disclosure and credit

Please allow a reasonable period for investigation, remediation, and deployment before public disclosure. We will coordinate disclosure timing with you where possible.

With your permission, we may credit researchers who responsibly disclose valid findings in a security fix note or coordinated disclosure. We will honor requests for anonymity and will not publish personal information without consent.

Credit does not imply bounty eligibility or payment. A researcher who remains anonymous can still receive credit, but cannot receive a bounty payment. See [Bounty payment and identity verification](#bounty-payment-and-identity-verification).

## Acknowledgments

Researchers who report valid findings and consent to being named are listed here. Credit does not imply bounty eligibility or payment.

- **Md. Jakariya** — input validation on the x402 facilitator payment path, 2026-08

## Safe harbor

We will not pursue legal action against you for good-faith security research that follows this policy, provided that you:

- Avoid privacy violations, service disruption, and destruction or corruption of data.
- Do not move, withdraw, mint, or permanently lock real funds.
- Do not access or exfiltrate data beyond what is necessary to demonstrate the issue.
- Do not conduct denial-of-service, spam, or high-volume testing against production.
- Do not target users, employees, unrelated systems, or third-party providers.
- Report the issue to us before publicly disclosing it.
- Stop testing and contact us promptly if you encounter sensitive data, credentials, or evidence of active exploitation.

This safe-harbor commitment applies only to conduct that falls within this policy and does not authorize activity that violates applicable law or the rights of third parties.

## Important limitations

This policy does not create a contract, employment relationship, partnership, or entitlement to compensation. It does not require SBC to accept a report, recognize a vulnerability, deploy a fix, disclose an issue, provide ongoing updates, or pay a bounty.

SBC may modify this policy, its scope, its bounty practices, or its disclosure process at any time. The version in effect when a report is submitted will generally govern its review, subject to applicable law and the specific terms communicated by SBC.

Last updated: 2026-08-26
