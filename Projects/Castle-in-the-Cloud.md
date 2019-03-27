# Summary

The Castle-in-the-Cloud (or maybe Cyberspace Station) implements [Sovereignty-as-a-Service](https://blog.keys.casa/casa-is-sovereignty-as-a-service/), a virtual fortress to secure your passwords, private keys and personal information. As such your Castle will be home to your virtual identities (Agents) and it will be possible to mediate all your online interactions through your Agents in order to secure your identities and personal information.

# Architecture

![Castle in the Cloud](https://i.imgur.com/ijc9V68.png)

Technically the Castle is a suite of integrated services that run in [Docker containers](https://www.docker.com/) on a server, typically a [VPS](https://en.wikipedia.org/wiki/Virtual_private_server) but it can be self-hosted for additional security.

## ControlCenter

The ControlCenter is a service that manages all the other containers in the Castle. It is the first and only one that needs to be installed in a Docker instance. On startup it will download and run the rest of the containers in the suite.
In order to be able to manage other containers running in the same host the ControlCenter must be launched in a special mode (specifically a shared socket as described in this [Docker-in-Docker article](https://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/)).

The UI will present similar to a smart-phone with a desktop of icons for each service installed and the ability to install, manage and configure services like apps on a phone.

## GateKeeper

The GateKeeper is a reverse proxy service that mediates all external access to the other services running in the Castle. All requests for information or control of anything running in the Castle is authenticated, authorized, validated, routed and logged by the GateKeeper ensuring a specified trade-off between [security vs usability](Security-vs-Usability).

A typical implementation of the GateKeeper will run an instance of [nginx](https://www.nginx.com/), a high-performance load-balancer, web-server, and reverse-proxy. The GateKeeper may include an instance of [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) if the Castle is running on a [Kubernetes](https://kubernetes.io/) cluster.

## KeyMaster

The KeyMaster is responsible for storing all your private keys and passwords in a highly secure digital [vault](https://www.vaultproject.io/index.html) and integrating with other services, enabling varying levels of access to those secrets. 

The UX will appear as a skeptical Bayesian agent that trusts the user only to the extent of the information provided. For example if you wish to acquire read-only access the NextCloud service or to login to facebook through the AlterEgo social mediator you may request a link sent to your email address. Access to your email gives the KeyMaster a (say) 60% confidence level that you are who you claim to be. To get access to your email may require more evidence such as logging in from a known IP address which might give the KeyMaster a (say) 85% confidence. To spend Bitcoin from your full node wallet running the Castle may require even more evidence such as co-signing the transaction with a [hardware key](TBD) or [Casa Node](TBD) which gives the KeyMaster a (say) 99% confidence you are properly authenticated.

## Compository

The Compository is a structured hierarchy of git repositories. Each repo may contain other repos via the [git-subrepo](https://github.com/ingydotnet/git-subrepo) extension, hence a composite repository or "compository".

The Compository service will run an instance of [Gitlab](https://www.gitlab.com) (free) or [Github Enterprise](https://enterprise.github.com/) (commercial) in the container along with any number of integrated git functions. A git function is a service (also installed as a container) that is triggered by a [git hook](https://githooks.com/). It takes a git repo as input and generates another git repo as output. Typical git functions include static web site generators such as [Jekyll]() and [Gatsby](), and continuous integration services such as [Jenkins](). Integrating these services enables you to publish a portfolio site or a blog (for example) by pushing a commit to a Gatsby source repo, like a self-sovereign version of [Netlify](https://www.netlify.com).

The Compository will come initialized with all the source code for a new Castle.

## Meridion

The Meridion service implements a UI to any number of [Nomicon](Nomicon) games. Each game will store a local version in the Compository and integrate with an equity-enabled blockchain (such as [OCEAN](OCEAN)) through an adapter to manage ownership of game assets and archive records for posterity.  

The Compository will contain an initial Nomicon to govern the self-sovereign Castle.

## OCEAN

[OCEAN](OCEAN) is an equity-enabled blockchain forked from Equibit. 

## Blockchain nodes

Containers to run full nodes such as [Bitcoin](TBD), [Ethereum](TBD), [OmniLayer](TBD) and [RavenCoin](TBD) will be easy to install and integrate with the KeyMaster which will act as a multi-currency wallet for all. 

## ExoCortex

The ExoCortex service will store and organize all your private notes, like a self-sovereign version of [Evernote](https://www.evernote.com). It may be optionally connected to Evernote (or [Google Keep]() or [Microsoft OneNote]() or related services through custom adapters) for import, backup and sync operations so you can continue using whatever UI is most convenient.  

Future versions of ExoCortex may include an AI that has direct access to your notes. Your AI agent can increasingly behave like you to external observers as the technology progresses.

## NextCloud

Installing the [NextCloud]() service will provide a self-sovereign version of [DropBox](https://www.dropbox.com).
Additionally it may be integrated with the GateKeeper so that shared links may require configurable authentication and authorization from other Castles.

## AlterEgo

The AlterEgo service is a social mediator. You can create any number of virtual identities such as separate ones for work, gaming and family. When you login into a social media platform such as [facebook]() or [twitter]() through AlterEgo it will mediate all interactions, log all events, backup all posts, and protect your privacy. All passwords for external platforms are secured in KeyMaster's vault.

## Email

Integrated with KeyMaster via AlterEgo, the Email service can be run stand-alone or sync with external email services like Gmail through adapters to import and backup all your electronic correspondence.

Email may also integrate with other Castle services such as creating a new ExoCortex note by sending email, or voting on a Nomicon issue by responding to a special email, or logging into a social media account by following a link sent via email, etc.

# Use Cases

## Project Governance

The initial use case for Castles is to enable distributed secure project governance via Meridion.
A project is a special hierarchical git repo composed of a Nomicon game and optionally but usually one or more code repos.
The game specifies the project's policies, goals, requirements and design in a set of source files that are used as input to a static website generator.
Any changes to the project are submitted as proposals, reviewed by the stakeholders, iterated on to incorporate feedback and ultimately merged to the project (just like the [git workflow](https://guides.github.com/introduction/flow/) for software development) according to the rules of the game.
All aspects of the project, including the rules themselves, are codified in the project and therefore amenable to same process of specification, development, debugging and review.
At any given time the current state of the project is accessible in its generated web site.

When a new project is created, the original Castle is the sole owner.
At the time of creation the owner may specify an equity blockchain (such as [OCEAN](OCEAN)) to track ownership and archive records related to the project, most importantly the HEAD commits of the published branches which define the current state of the project.

Solo projects may find Meridion useful but the real value proposition comes in when others are invited to collaborate on the project.
For this example imagine that six other Castles (representing individuals or organizations) are invited to join the project as directors to help guide the project to profitability:

![castles](https://i.imgur.com/M41DMQE.png)

Issuing shares in the project is analogous to issuing shares in a company. 
The original owner of the project decides how many shares to issue and these are created on the specified equity blockchain (through an adapter since different blockchains will publish different APIs for similar tasks).
Meridion will keep an owners list updated in the project web site, displaying the shares owned next to each Castle's flag.
The project site may be kept private or shared with selected groups or published.

Voting on proposals will be managed via Proof-of-Stake (PoS) or eventually Proof-of-Proxy (PoP). 
When a new proposal is published all Castles will be notified automatically and the proposal will be copied to each Castle's Compository where it can be reviewed and evaluated.
Votes will be signed by the local KeyMaster and submitted back to the proposal's origin.
Results of votes (typically only commit hashes) will archived on the blockchain for posterity and auditability.

## Sovereign Household

Security is a hard problem, really hard because it never-ending arms race between the opposing sides.
Even security professionals find it difficult to keep their private keys private, safe and accessible.
The vast majority of people online don't have the knowledge or skills so they outsource to private companies like Facebook and Google at the expense of their privacy. The users are the product, not the customers.

This is why Tim Berners-Lee, inventor of the world wide web is [on a mission](https://phys.org/news/2019-03-years-berners-lee-mission-internet-ills.html) to fix the problems of online abuse, misinformation and data protection that were not envisioned when the system was created decades earlier. 
His idea is a new platform called [Solid](https://solid.mit.edu/) (for SOcial Linked Data) and his new company [Inrupt](https://solid.inrupt.com/) provides PODs (Personal Online Datastore) for consumers. 
Castles can implement the [Solid specifications](https://github.com/solid/solid-spec) in order to become a kind of POD and join Berner-Lee's vision. 

## DAOs and DACs

Future companies will not be corporations (entities of the State), rather they will be self-sovereign firms operating in [Cyberspace](https://www.eff.org/cyberspace-independence) flying under the flag of [Ulex](https://medium.com/chainrift-research/ulex-an-open-source-legal-system-6a05481b686f) or a value-oriented Consortium or any number of voluntary alliances. 

The [Aragon Project](https://blog.aragon.org/introducing-aragon-unstoppable-companies-58c1fd2d00ce/) has a consistent vision (and a very nice UI) built on [Ethereum](https://www.ethereum.org). 
[Meridion](Meridon) projects will provide a similar suite of services but Meridion is intended to be blockchain-agnostic (any blockchain that supports equities, securities or [NFTs](https://en.wikipedia.org/wiki/Non-fungible_token) such as [OCEAN](OCEAN) should be usable through custom adapters).
One significant difference that is anticipated is that smart contracts will be executed locally with only the results posted to the blockchain rather than executing smart contracts on the blockchain. 
Implications of this architectural difference are TBD.

## Intra-corporate Economy

The great irony of modern capitalism is that companies compete in a market but internally they look a lot more like a feudal system with a hierarchy of modern-day aristocrats (management) using office politics to fight over turf and power.
Historically markets replaced feudal systems for a reason, the competition benefits the customer over the producer and the point of economic activity is value creation, not rent-seeking, at least ideally.

Imagine instead if every team within a company had its own Castle and traded with other teams, exchanging deliverables and services for crypto-tokens in an intra-corporate economy.
When the stakeholders have [skin in the game](https://medium.com/incerto/what-do-i-mean-by-skin-in-the-game-my-own-version-cc858dc73260), decisions become less about politics, optics, and posturing and more about rational trade-offs, honest negotiations, and value creation.

# Related Projects

* [Open Index Protocol](https://oip.wiki/Main_Page)
* [Solid](https://solid.inrupt.com/)
* [Casa](https://keys.casa/) "Keep your digital castle secure"
* [urbit](https://urbit.org/) "A personal server built from scratch"
* [sandstorm](https://sandstorm.io/) "an open source platform for self-hosting web apps"
