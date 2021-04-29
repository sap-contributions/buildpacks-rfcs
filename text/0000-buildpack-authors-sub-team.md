# Meta
[meta]: #meta
- Name: Buildpack authors Sub-team
- Start Date: 2021-04-29
- Author(s): [@hone](https://github.com/hone), [@samj1912](https://github.com/samj1912)
- RFC Pull Request: (leave blank)
- CNB Pull Request: (leave blank)
- CNB Issue: (leave blank)
- Supersedes: (put "N/A" unless this replaces an existing RFC, then link to that RFC)

# Summary
[summary]: #summary

This RFC proposes the creation of a "Buildpack authors" sub-team which will be dedicated to maintaining tools that help buildpack authors create buildpacks. This can include language bindings like [libcnb](https://github.com/buildpacks/libcnb) (and similar bindings in other languages like python, bash or rust), tooling for testing buildpacks and project templates that enable authors to quickly bootstrap.

# Definitions
[definitions]: #definitions
sub-team - Sub-teams are responsible for narrower sets of concerns related to specific aspects of the project. Each sub-team will include at least one core team member to help align with the broader roadmap.
Language bindings: A library that provides language specific constructs to make interaction with the buildpack API easier. 

# Motivation
[motivation]: #motivation

- Why should we do this?

The Cloud Native Buildpacks project itself doesn't maintain any buildpacks. Rather, it provides the specification, tooling and infrastructure to create, discover and interact with buildpacks and the ecosystem surrounding them. 

Providing well-maintained, spec-conformant and reliant language bindings, tools and utilities to allow buildpack authors to easily interact with the buildpack API rather than having them to recreate them closely aligns with the goals of the project.

Currently, the project only provides go bindings for the buildpack API via [libcnb](https://github.com/buildpacks/libcnb).

libcnb is currently under the purview of the implementation team, however historically, the majority of the efforts of the implementation team have been focused on maintaining the lifecycle. As such, libcnb currently doesn't have well-defined processes around how it should be maintained.

As the project matures and as more and more authors start creating buildpacks, the need for a Buildpack authors team becomes increasingly evident.

- What use cases does it support?

The team is expected to support and maintain language bindings for popular languages that buildpack authors typically use and related libraries and tooling like language specific project templates or test utilities.

We have already seen people related to the project create and maintain their own language bindings for the buildpack API in [rust](https://github.com/Malax/libcnb.rs), [python](https://github.com/samj1912/python-libcnb) and [bash](https://github.com/jkutner/libcnb.bash).

There are also alternative go bindings like [packit](https://github.com/paketo-buildpacks/packit) and extensions to libcnb like [libpak](https://github.com/paketo-buildpacks/libpak) which provide useful utilities on top of libcnb.

These bindings typically need to be accompanied by language specific templates (which can be exposed and used by `pack buildpack new`) that can be used to properly package and test buildpacks. Examples include libraries like [occam](https://github.com/paketo-buildpacks/occam) which is used for integration testing of buildpacks written in golang. 


- What is the expected outcome?

A Buildpack authors sub-team is formed or an existing team takes ownership of the above responsibilities.

# What it is
[what-it-is]: #what-it-is

The Buildpack authors team will be dedicated to maintaining tools that help buildpack authors create buildpacks. This will include language bindings like [libcnb](https://github.com/buildpacks/libcnb) (and similar bindings in other languages like python, bash or rust), tooling for testing buildpacks and project templates that enable authors to quickly bootstrap.

It will own the following repos:

- libcnb (the current Golang binding and any future additions for other languages)
- Buildpack project templates which can be used by pack
- Buildpack testing libraries

# How it Works
[how-it-works]: #how-it-works

The Distribution sub-team will follow the same guidelines as other sub-teams:

- include at least one core team member
- responsible for narrower sets of concerns related to specific aspects of the project

# Drawbacks
[drawbacks]: #drawbacks

Why should we *not* do this?

- More teams
- May be difficult to sustain maintainers for all these teams

# Alternatives
[alternatives]: #alternatives

**Do Nothing**
Not an option because we would have unmaintained repositories

**Grow the Distribution or Implementation Team**
We could move these repos under the Distribution or Implementation team, and grow the list of maintainers.

# Prior Art
[prior-art]: #prior-art

- [Distribution team](https://github.com/buildpacks/rfcs/blob/main/text/0062-distribution-team.md)
- [Platform team](https://github.com/buildpacks/community/blob/main/TEAMS.md#Platform-Team)

# Unresolved Questions
[unresolved-questions]: #unresolved-questions

- Who are the maintainers?
- Who are the contributors?