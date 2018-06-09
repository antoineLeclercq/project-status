# Scott Bellware Work Log

## Fri Jun 08 2018
- Finished retrieval server functions
- Bechmarked gets (No regression due to server functions)
- Removed database scripts and tools to their own package

## Thu Jun 07 2018
- Retrieval server functions

## Wed Jun 06 2018
- Started working on retrieval server functions

## Tue Jun 05 2018
- Advisory locks and benchmarks

## Mon Jun 04 2018
- Put and get benchmarks for message_store-postgres
- Struggled with Advisory locks
- Nathan found the issue, being that the session-level lock is released before the transaction is committed, which happens in the client only after the server function has terminated
- Switching to a transaction-level lock was the solution
- Benchmarked the put and get operations both before and after the advisory lock implementation

## Sun Jun 03 2018
- Put and get benchmarks for message_store-postgres
- Advisory locking isn't serializing the writes
- Worked on various implementations of the locks trying to find why it's not working as I'd expected

## Fri Jun 01 2018
- Put and get benchmarks for message_store-postgres
- Adjustments to diagnostics-sample to support message_store-postgres benchmarks

## Thu May 31 2018
- Put and get benchmarks for message_store-postgres
- Adjustments to diagnostics-sample to support message_store-postgres benchmarks
- Established patterns for benchmarking

## Wed May 30 2018
- Put and get benchmarks for message_store-postgres

## Wed May 30 2018
- Put and get benchmarks for message_store-postgres

## Sat May 5 2018 - Sat May 12 2018
- Workshops in Toronto

## Fri May 4 2018
- Prep for class in Toronto
- Printing
- Review materials

## Wed May 2 2018
- Completed applying project standards to Settings

## Tue May 1 2018
- Applying project standards to Settings

## Mon Apr 30 2018
- Found that Settings is not brought up to project standards
- Started applying project standards to Settings

## Sun Apr 29 2018
- Integrated Reflect into Validate

## Fri Apr 27 2018
- Integrated Reflect into Transform

## Thu Apr 26 2018
- Completed integrating Reflect into Virtual
- Documentation

## Wed Apr 25 2018
- Started integrating Reflect into Virtual

## Tue Apr 24 2018
- Message facts
- Will Howard's change to the output of the message dump
- Changed the utility name to evt-pg-print-messages
- Francesco found and fixed a potential data type boundary problem with the Postgres implementation

## Fri Apr 20 2018
- Documentation

## Thu Apr 19 2018
- Documentation

## Wed Apr 18 2018
- High-level outline of docs site and placeholder pages
- Facts, rather than FAQs
- Service facts

## Tue Apr 17 2018
- Documentation of streams
- Assessed Docusaurus and MkDocs. Both missed the mark. Went back begrudgingly to GitBook.

## Mon Apr 16 2018
- Documentation of streams

## Sat Apr 14 2018
- Communicated with Nathan about TTY detection in the Log library
- Nathan offered to look into it
- TTY detection is a blind spot for me
- I took time to familiarize myself with how TestBech does it
- Implemented in in the Log library

## Fri Apr 13 2018
- Completed telemetry and logging for Retry
- Communicated the basic to Sam Stickland
- Found issue in Log library where colors codes are present when device is not a TTY

## Thu Apr 12 2018
- Started work on the Retry library, and integrating Telemetry into it, as well as enabling it to be used as a dependency
- Wrote project update

## Wed Apr 11 2018
- Integrated Reflect into SubstAttr, including support for ancestor lookup

## Tue Apr 10 2018
- Reconsidered the suspension of the SubstAttr effort
- Talked with Nathan, and agreed that the ancestor lookup is a correct feature for Reflect
- Added support for ancestor lookup to Reflect

## Mon Apr 9 2018
- Realized that Reflect is a poor fit for SubstAttr
- SubstAttr needs to use the variant of `const_get` that considers constants in ancestors
- Suspended the effort
- Added direct support for SubstAttr::Substitute to Dependency

## Sat Apr 7 2018
- Closed test coverage gap on inner reflection having it's strictness set as an argument to the `get` call
- Looked at test-bench to see if I could integrate Reflect into it. Will wait on guidance from Nathan as to whether he wants this
- Started integrating Reflect into SubstAttr

## Fri Apr 6 2018
- Met with Ashley to get resources in-place for converting the tutorial to a self-paced training document
- Completed integrating Reflect into Validate

## Thu Apr 5 2018
- Integrating Reflect into Validate
- Retro-fitting some new requirements into Reflect that have emerged from working in Validate

## Wed Apr 4 2018
- Started integration of Reflect into Validate

## Tue Apr 3 2018
- Completed integration of Reflect into Transform

## Mon Apr 2 2018
- Integrating Reflect into Transform

## Sun Apr 1 2018
- Completed first operational increment of the Reflect library
- Started integrating Reflect with Transform

## Fri Mar 30 2018
- Reflect library

## Thu Mar 29 2018
- [decision] Protocol should have been Reflect
- The Reflect implementation should be focused only on reflection
- [realization] The protocol discover can't be generalized across all scenarios
- Only the reflection part can be generalized (inner constants and accessor methods)

## Wed Mar 28 2018
- Started work on integrating the Protocol library into the Transform library
- Met with Nathan to catch up and do a bit of planning
- Once deep into the transform code, I realized (remembered) how different it's use of protocol discovery is, and that the Protocol library isn't sufficient
- Suspended work on Transform while closing the gap with Protocol
- Protocol now has a `strict` parameter that varies the behavior when parts of the protocol are not discoverable. It will either raise an error or return nil.
- Continued elaborating Protocol
- Need to add the capability to Protocol to check that the protocol implementation accessor (or any method) is present, but without invoking it.
- Will create a `Check` namespace that does protocol namespace discovery, and then tests to see whether the accessor is implemented.
- Conversely, I could just use the raw internals of Protocol from Transform
- Will get further into the details tomorrow

## Tue Mar 27 2018
- Finished first implementation of the protocol library
- Will start on its integration into the transform library tomorrow

## Mon Mar 26 2018
- Protocol library

## Sat Mar 24 2018
- Removed from consideration the removal of transient attributes. They are used to provide type checking for regular assets.
- Started in protocol discovery library

## Fri Mar 23 2018
- Weekly online meetup
- Forgot about documentation meeting with Ashley. Rescheduled to Fri Apr 6.
- Removed default values capability from initializer
- Remediated issue with schema attributes where assigning a nil to an attribute with a default value would reset the value to the default rather than retain the nil value
- Started looking into the removal of transient attributes

## Thu Mar 22 2018
- Chatted with Alexander about the issue on the casing library
- Reviewed and merged Billium's pull request on the log library
- Annotated the issue filed on the cycle library to make it more approachable as an entry-level work item
- Updated the website's contributor's page
- Founds and removed vestigial gems on the Eventide rubygems.org account
- Started on the component generator issues

## Wed Mar 21 2018
- Wrote project update
- Did work items (and closed PRs) on the workshop setup instructions that were submitted by participants in the Victoria workshop

## Tue Mar 20 2018
- Revisions of contributor guide and supporting materials
- Announced contributor guide
- Polled community for interests in materials and articles
- Prioritized and categorized work items

## Mon Mar 19 2018
- Completed first draft of contributor guide

## Sun Mar 18 2018
- Contributor guide

## Fri Mar 16 2018
- Contributor guide

## Thu Mar 15 2018
- Contributor guide

## Web Mar 14 2018
- Made corrections to website copy
- Corrected entity level label
- Removed help wanted label
- Started contributor guide

## Tue Mar 13 2018
- Reviewed presentation flow for Wroc_love.rb with Nathan. Good stuff. Better foundation for general-audience talk building on the presentation from Explore DDD.

## Thu Mar 8 2018
- Explored options for creating a 64-bit number from a stream name to use as the ID for an advisory lock
- Got an answer on Twitter from Greg Navis (@gregnavis) that uses MD5.
- Talked over the solution with Josh and we're both comfortable with the approach and the implications
- Continued the discussion on the Eventide Slack org about security and encryption
- Added issues to GitHub repos that I had been keeping track of only in my notes

## Wed Mar 7 2018
- Completed the standardization of issues labels in the eventide-project and eventide-examples orgs
- Re-tagged existing issues with new labels
- [realization] "Problem" label is insufficient for categorizing things that are mistakes
- Added the "mistake" label, and adjusted the color of the problem label
- Set up ZenHub. One of the worst inception user experiences imaginable.

## Tue Mar 6 2018
- Maintenance of contributor-assets in preparation of adding label standardization scripts
- Removed obsolete repositories: work-log and planning
- Created project-status repository for housing aggregated status updates as well as work logs
- Added project-status channel to Slack
- Installed "new" GitHub integration into Slack for project status commit notifications for the project-status repository
- Wrote project status update and informed the community of it
- Created documentation-request repository, and informed the community of its existence and use
- Started work on tool to set label names, colors, and descriptions for all GitHub repositories
- Will test with a fresh mind tomorrow before running it against the eventide-project org

## Mon Mar 5 2018
- Reviewed and merged Josh's correction to the error message text when an entity store is not properly configured with a projection
- Reviewed all open issues
- Reviewed all of the variant labels and colors used across all repositories
- Established label standards, and let Nathan know

## Sun Mar 4 2018
- Got together with Nathan to get re-oriented to work suspended in December
