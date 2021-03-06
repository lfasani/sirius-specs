# Sirius Evolution Specification: Title of the evolution

## Preamble

_Summary_: a short one-sentence summary of what this evolution is about.


| Version | Status | Date       | Authors   | Changes           |
|---------|--------|------------|-----------|-------------------|
|    v0.1 |  DRAFT | 2015-01-05 |   pcdavid | Initial version.  |

The possible status are (roughly inspired by [PEP-0001](http://python.org/dev/peps/pep-0001/):

* *DRAFT*: Initial version and revisions based on internal feedback and discussions. They have version numbers 0.x.
* *PROPOSAL*: When the document is considered ready for discussion with the community, it becomes a PROPOSAL. The first such version is numbered 1.0. Feedback from the users/clients are integrated in further versions 1.x which are still PROPOSALs. Changes from one version to the next should be documented inside the document.
* *ACCEPTED*: Once agreement has been reached, the document becomes ACCEPTED.This version becomes the authoritative one for guiding the evolution's actual implementation. It should normally be considered freezed. Any change to it should be exceptional and subject to approval by the project manager. Such changes must be clearly documented and justified.  
* *ARCHIVED*: Once the evolution has been implemented _and_ its specification has been integrated into the reference documentation, this document is ARCHIVED. Any further change to the same features should be another evolution.

_Relevant tickets_ (links to the Bugzilla tickets which are related to the change):

* [Bug 456410 - Define and use alternate APIs for high-level model queries that can be extended/customized when appropriate](https://bugs.eclipse.org/bugs/show_bug.cgi?id=456410)

## Introduction

This section should contain a summary of the proposed evolution, including why it is needed. Ideally it should be self-contained so that non-developers can get a quick overview of the evolution without reading the detailed specification. 

## Detailed Specification

This section contains the "meat" of the document. Its structure will depend on the evolution itself, but it should contain:

* a clear description of the objective, i.e. why the evolution is needed.
* a justification of the approach chosen. If other approaches were considered and rejected, document it for future reference.
* limits: things that are out of the scope of the evolution.

## RCP/Web Flavors Compatibility and Interoperability

This section clearly states to which extent the feature will be present in / the change impacts the RCP flavor, the Web flavor, or both. If it supports both, the section should describe the technical impact of doing so. For example it may imply refactoring some existing code to make its core behavior available on both flavors, or abstracting a common API for which two separate implementations will be needed.

## Backward Compatibility and Migration Paths

Every one of the sections below should be present. Even if there is no corresponding change (for example no API change), it should exist to mention explicitly "This evolution does not change any API."

### Metamodel Changes

Document any change to the Sirius metamodel. If they require a migration operation, mention it and describe the general idea of how migration process. If any information can be lost during the migration, mention it clearly. If validation rules must be added/modified, mention it also.
  
### API Changes

List every API addition, removal and deprecation. For each removal and deprecation, indicate the migration path for existing code. If you plan to depcrecate an existing API, it is your responsibility to update all our existing code to use the alternative you provide; take this into account in the estimation for the task.

Be careful when designing new APIs to provide all the appropriate "hooks" for users to customize the feature's behavior. In particular, think carefully about which of the methods you provide should be @protected@ instead of @private@ so that users can override some of the default behavior. Do no hesitate to discuss this wth the users  who requested the feature to make sure he will be able to implement the customizations he needs.

### User Interface Changes

List every user-visible change in the interface. Here "user" includes not only end-users but also specifiers which use the VSM editor.

### Documentation Changes

List every documentation needing an update here, starting by the New and Noteworthy documentation.

## Tests and Non-regression strategy

This part of the document should describe the strategy to use to correctly test the evolution and guarantee the non-regression.  

## Implementation choices and tradeoffs

Any important tradeoff or choice made during the implementation should be referenced here with pros/cons leading to the final decision.
