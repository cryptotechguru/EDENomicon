# Cryptonomicon

1. The name of the [game](./Nomicon/) is Cryptonomicon
1. The goal of the game is to grow adoption of the [Equibit protocol](https://arxiv.org/abs/1612.06953)
1. The players of the game are the members of the [Cryptonomicon team](https://github.com/orgs/Equibit/teams/cryptonomicon/members)
1. All players must unanimously agree to all rule changes
1. Proposals may add, amend or repeal a rule
1. All rules should be logically self-consistent 
1. The source for the rules are kept in the [website repository](https://github.com/Equibit/Cryptonomicon)
1. The rules are published on the [website](https://equibit.github.io/Cryptonomicon/)

## Conventions

1. The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in these rules are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

## Projects

1. A project is a sub-game that inherits from the base rule set of Cryptonomicon
1. A project MUST have a unique name
1. A project is located in a sub-folder of Cryptonomicon named after the project
1. A project MAY override a rule in the base game only if the rule is tagged as #virtual
1. A project MAY have its own set of players that MUST be a subset of the Cryptonomicon players
1. A project MUST have a charter document that defines that goals of the project
1. A project SHOULD be a collaborative game played between two teams, typically the Gatekeepers and Keymasters
    1. The Gatekeepers (representing the project customers) SHOULD be responsible for acceptance criteria for project deliverables
    1. The Keymasters (representing the project vendors) SHOULD be responsible for developing the project deliverables 

## Roles

1. A role is a function performed by a player (or their delegate) that comes with special rights and responsibilities.
1. Only players may fill roles.
1. For a role nomination proposal to pass, the player nominated MUST give their explicit approval. (No voluntelling!)

### Operator

1. The Operator role has the responsibility to carry out the provisions of the rules that are not yet automated.
1. The Operators of the game are specified in the [CODEOWNERS](https://github.com/Equibit/Cryptonomicon/CODEOWNERS) file.

