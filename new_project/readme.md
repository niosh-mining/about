# Github Release Process

This directory delineates the process, guidelines, and requirements for releasing 
new projects to the [niosh-mining github page](https://github.com/niosh-mining).

# Pre-Review Requirements

Before starting the github release approval process, please ensure the candidate code satisfies the
following requirements:

  1. The code is stored in a git repository
  2. The repo does not include any [nonpublic (sensitive) data](#Data) (consider removing old git history).
  3. The repo includes [documentation appropriate to the maturity of the software](#Documentation).
  4. The code includes a [testing procedure](#Testing).
  5. The code includes an [OSI approved open-source liscense](https://opensource.org/licenses).
  6. The code includes a [version string and a versioning system](#Versioning)
  7. The code has been uploaded to the niosh-mining github page as a **private** repo.

# Initiating a Review

After the requirements mentioned in this document are met, open a new issue in the
candidate repo (which is still **private**) entitled "Open Source Review". Copy the
contents of the [open_source_approval template](approval_template.md) as the body of
the issue and follow the directions and checklist.

# Guidelines

The following provide more details about specific guidelines for the candidate
open-source software projects.

## Documentation

The amount/type of appropriate documentation can vary widely based on the type/function
of the software and its maturity level. At a minimum, a readme file should be included
which includes the following:

  * The purpose of the software.
  * An indication of the software's maturity (eg alpha, beta, etc.)
  * A link to the [NIOSH about page/disclaimer](https://github.com/niosh-mining/about).

You should also strongly consider adding the following:

  * Instructions for installing the software
  * Instructions for contributing to the software
  * Quickstart guides/examples
  * Technical references

when it makes sense to do so. 

## Testing

Testing is essential to ensure software functions as intended. Best practice is to
develop a suite of automated tests which can be used to help vet proposed code changes,
guard against bug regression, and test dependency compatibilities. However, it is not 
always feasible to develop an extensive suite of automated tests (especially for highly
graphical applications). In these circumstances, clearly defined instructions for running
manual tests should be included.

## Data

Software projects should not include any nonpublic (sensitive) information. Nonpublic 
information in this instance is any information that has not previously been published.
Examples incude, but may not be limited to:
 - Personally identifiable information (PII) or other sensitive data,
 - unpublished research data,
 - data protected by a non-disclosure or other written agreement,
 - data that may be considered trade secrets,
 - user credentials, or
 - system-specific information (ip addresses, ports, protocols, etc.).

If data need to be included, for example to enable testing, it is best to use anonymized, 
fictitious, or public data.

## Versioning

Recommended versioning is largely based on [semantic versioning](https://semver.org/) 
consisting of four components:

[a.b.c.d]

where:

[a] is the Major Version. This number is set by application stakeholders and IT development based on the major feature set and design of the software.
	This would include compatibility breaking changes.

[b] is the Minor Version. Set by stakeholders and IT development based on incremental improvements and feature enhancements to the core application design.
	This would also include larger bug fixes.

[c] is the Revision of the software. Typically this number represents the quantity of times a release has been deployed to a production environment (or public download)
	This typically would include minor bug fixes.
	Note that all internal formal documentation, approvals and published help documentation or other writings will list [a.b.c] as the version number for the release.

[d] is the (optional) Build Number. This number is set internally by IT development and is based on configuration and build changesets.
	It is used by IT development for internal testing purposes and to match specific source repository changes to when a build occurred.
