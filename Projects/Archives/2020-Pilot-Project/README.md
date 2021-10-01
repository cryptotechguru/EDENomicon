# EDEN Protocol - 2020 Pilot Project

Join the pilot by filling out the <a href="https://forms.gle/E8QujYspeRxM1PEU7">questionnaire.</a> 

## Pilot Goal:

To trace product history in real-time by notarizing quality claims as the product is
transformed and moves along supply chain actors.

## Pilot Benefits:

Notarizing product claims generates multiple benefits:

1. Real-time product traceability
1. Link quality claims to digital evidence
1. Notarises terroir, cultivar, location, and other basic information.

## Possible Pilot Actors:

- Seed IP Owner
- Nursery
- Growers
- Analysis lab
- Genetics lab
- Productization (oils, creams, eatables, etc)
- Clinics and Dispensaries
- Patients and Customers

## Generic Pilot Scenario:

This scenario describes a step-by-step use of EDEN by a _Farmer_, a _Lab_, a _Consumer_, and an _Analytics Company_. 

- [2020 EDEN Pilot Example](https://nomicon.edenprotocol.io/Projects/2020-Pilot-Project/EDEN-Pilot-Example.html).

## Pilot Outcome:

We want to be able to associate quality claims across the supply chain.
This not only demonstrates product provenance but also allows claims to
be used as evidence for other claims.

## Technical Background:

The dynamics of this "web of trust" are described here: https://www.weboftrust.info/

For our supply chain purposes, we only need to implement the following features:

    Define container data structure
    Ability to create a profile ID.
    Ability to associate claims with the profile ID.
    Ability to create a new product batch history ID.
    Ability to make a claim about a specific batch history ID.
    Ability to forward (or follow) history ID to the next supply chain actor.
    Ability for next actor to make a claim about the history ID.
    Ability for actors to associate a claim with other claims as supporting evidence.

## Next Steps:

Using the EDENomicon process, we should collaborate to create our pilot *requirements*, *technology assessments*, *user interfaces*, etc.

Protocol definition will be managed as a separate project that COULD use this pilot project as its [Gatekeeper](https://nomicon.edenprotocol.io/Roles/Gatekeeper/). Let's see if we can define a **Project-as-a-Role** relationship in the Nomicon.
