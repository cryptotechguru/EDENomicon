@@ -0,0 +1,48 @@
# EDEN Protocol Definition Project:

## Project Goal:

To define and implement a simple decentralized web-of-trust protocol that tracks product history,
allows peers to notarize product claims, and allows peers to associate evidence to claims on an immutable ledger.

## What is a Web-of-Trust?

A WoT is the basis for all future capabilities required to achieve the EDENomicon goal.

The web-of-trust defines the relationship between any two peers on the network.
This relationship represents the degree of separation between peers that do not know one another.
The relationship is magnified by repeated transactions between peers that transact regularly.

>"As time goes on, you will accumulate keys from other people that you may want to designate as
>trusted introducers. Everyone else will each choose their own trusted introducers. And everyone
>will gradually accumulate and distribute with their key a collection of certifying signatures
>from other people, with the expectation that anyone receiving it will trust at least one or
>two of the signatures. This will cause the emergence of a decentralized fault-tolerant
>web of confidence for all public keys."
>                             -- *[Phil Zimmermann](https://en.wikipedia.org/wiki/Phil_Zimmermann), PGP manual (1992)*

In other words: *any network peer will be able to calculate their level of trust in another peer.*

This will enable the assessment of quality claims made by other peers on the network.
Brands will be encouraged to post their network identity(ies) on their website to demonstrate
evidence for the unique qualities of their product.

The desired dynamics are defined in great details in the [Rebooting the Web of Trust - RWOT](http://www.weboftrust.info/specs.html) specifications.

Our project should be an *adaptation* of a *subset* of the specifications published by the RWOT team.

## Requirements specifications

Specific implementation requirements should be driven by the needs of the [2020-Pilot-Project](../2020-Pilot-Project). The [EDEN-Pilot-Example](../2020-Pilot-Project/EDEN-Pilot-Example.md) documents a simple use scenario involving a farm, a lab, and a customer.

Technical requirements definition, protocol design, and an [OSS](https://en.wikipedia.org/wiki/Open-source_software) reference implementation should be managed under the EDEN Protocol Definition project. Discussion will be held in [Issue #12](https://github.com/cryptotechguru/EDENomicon/issues/12).

## Reference implementations

Our reference solution will necessarily include the selection of specific technology platforms and networks. The protocol itself is platform-agnostic.

## Development Financing

Initial efforts by [EDENomicon players](https://nomicon.edenprotocol.io/Roles/Player/) and [EDA members](http://theethicaldataalliance.org) are currently performed on a voluntary basis.
Various financing models are being reviewed. The [EDENomicon Bounty Protocol](https://nomicon.edenprotocol.io/Projects/Bounties/) COULD be used as a model to define project funding
milestones and review process.