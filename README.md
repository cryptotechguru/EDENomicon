# EDENomicon

1. The name of the [game](./Nomicon/) is EDENomicon.
1. The goal of the game is to implement and coordinate ongoing development of the Ethical Data Exchange Network protocol.
1. The players of the game are the members of the [players team](https://github.com/orgs/cryptotechguru/teams/players/members).
1. All rules should be logically self-consistent.
1. The source code for the game is maintained in the [website repository](https://github.com/cryptotechguru/EDENomicon).
1. The game is published on the [website](https://cryptotechguru.github.io/EDENomicon/).

## Jurisdiction

1. Only [Ulex 1.2](https://ulex.law/versions/1.2) governs any claim or question arising under or related to this agreement, including the proper forum for resolving disputes, all rules applied therein, and the form and effect of any judgement.

## Conventions

1. The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in these rules are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

## Process

1. All players must unanimously agree to all rule changes.
1. All changes to the game MUST be submitted through a pull request (PR).
1. All changes to the game SHOULD be vetted by submitting an [issue](https://github.com/cryptotechguru/EDENomicon/issues).
    1. An issue is an inconsistency between a specification and an observation (analogous to a bug in software).
    1. If any player breaks the rules or witnesses another player breaking the rules, they SHOULD open an issue.
    1. Issues SHOULD be reviewed by the Operators to determine whether the rule should be changed or the player should be sanctioned.
1. Only players may fill [roles](Roles/).
1. If a proposal offers a choice between two or more options an Operator should call a [multi-vote](multi-vote.md).

## [Projects](Projects/)

1. A project is a sub-game that inherits from the base rule set of EDENomicon.
1. A project MUST have a unique name.
1. A project MAY be located in a [sub-folder](Projects/) named after the project.
1. A project MAY override a rule in the base game unless the rule is tagged as #final.
1. A project MAY have its own set of players. 
1. A project SHOULD have a charter document that defines that goals of the project.
1. A project SHOULD be a collaborative game played between two teams, typically the [Gatekeepers](Roles/Gatekeeper) and [Keymasters](Roles/Keymaster)
    1. The Gatekeepers (representing the project customers) SHOULD be responsible for acceptance criteria for project deliverables.
    1. The Keymasters (representing the project vendors) SHOULD be responsible for developing the project deliverables.
1. A project MAY be funded with [Bounties](Projects/Bounties).
