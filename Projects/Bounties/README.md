# Bounties

1. Bounties provide a mechanism for funding tasks.
1. Tasks are tracked as [issues](https://github.com/cryptotechguru/EDENomicon/issues).
1. The bounty MUST get its own page which includes:
* name (Bounty-#) where # is the issue #
* associated issue and deliverables link
* lead [Gatekeeper](/Roles/Gatekeeper)
* lead [Keymaster](/Roles/Keymaster)
* assigned [Treasurer](/Roles/Treasurer)
* associated project link
* requirements
* estimate & funding

## Process

The players involved SHOULD marshal the bounty through the following standard [project](https://github.com/cryptotechguru/EDENomicon/projects) stages:

### Triage Stage

1. The bounty's wiki page and corresponding issue are created and cross-linked.
1. Requirements (acceptance criteria) are managed by the Gatekeeper.
2. Active Players are defined in the Bounty by the Gatekeeper.
3. The Gatekeeper and Keymaster define payment allocation between Active Players.
4. Each Player involved must declare a payment currency (USD or FIL).
5. When ready the Gatekeeper moves the issue to `Proposed` and hands off (assigns the issue) to the Treasurer.

### Proposed Stage

1. The Treasurer reviews the bounty's market value against planned deliverable value or comparable work in other markets. If out of line the Treasurer SHOULD send the issue back to `Triage`.
1. The Gatekeeper creates a crowdfund page on the pay server and publishes the corresponding link on the wiki page.
1. The Treasurer notifies Active Players that the bounty is approved and open for funding.
1. The Gatekeeper moves the issue to `In Progress` and hands off to the Keymaster.
1. If the bounty is rejected by the Tresurer, the Gatekeeper is responsible for communicating issues to Active Players, updating the wiki page and/or closing the issue.

### In Progress Stage

1. The Keymaster is responsible for delivering on the requirements.
1. The Keymaster should periodically update the issue with progress reports.
1. After the bounty is funded the requirements and/or payment allocation MAY only be updated if both the Gatekeeper and Keymaster approve the changes.
1. When ready the Keymaster updates the Deliverables section of the wiki page, moves the issue to `In Review`, and hands off to the Gatekeeper.

### In Review Stage

1. The Gatekeeper is responsible for testing deliverables against requirements.
1. The Gatekeeper opens separate issues for any deltas found, moves the bounty issue back to `In Progress` and hands off to the Keymaster.
1. If the requirements are all satisfied the Gatekeeper moves the issue to `Complete` and hands off to the Keymaster and Treasurer.

### Completed Stage

1. The Keymaster creates a payment request in the pay server and sends a link directly to the Treasurer.
1. The Treasurer verifies the request and sends the payment to the Keymaster.
1. When the payment is received the Keymaster closes the issue.

## Deliverable-Based Payments

1. Each deliverable has been estimated at 1/16th of the original $72,000 budget proposed in the [Metatron Open Grant Proposal](https://github.com/Flaxscrip/devgrants/blob/Flaxscrip-patch-1/open-grant-proposals/open-proposal-metatron.md)
1. Active Players can request payment in USD or FIL during the Triage Stage.
1. Payment for each deliverable is divided among Active Players based on latest approved Bounty allocation at the time of payment.
