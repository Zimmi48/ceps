Restructure and Improve Coq Reference Manual

Drivers: Jim, Matthieu, Théo

# Summary

The current Coq Reference Manual needs considerable work to better
serve the needs of the Coq community.  We propose a new chapter-level
working outline for the documentation and a process to manage
improving the manual.

# Motivation

Better documentation will encourage more people to learn, teach and
use Coq.  Less directly, it may also encourage more people to
contribute code enhancements and improvements to Coq.

We believe the documentation should be easily understood by users who
have only a bachelor's degree in Computer Science or Mathematics.
Users who are learning Coq should be able to use the manual as a
reference and exhaustive documentation without having to become expert
first.

Some of the more apparent issues with the current documentation are:
-	**Poor organization.** For example, the current split between the
     Gallina chapter and "Extensions of Gallina" is artificial.
     The material in "Syntax Extensions" and "Extended
     Pattern Matching", which are not contiguous with the Gallina
     chapters, should be integrated with the material in the Gallina
     chapters as well.
-	**Missing explanations of essential concepts.** For example,
     there's no section that describes how Coq does unification,
     nor is there a description of basic reductions such beta, delta,
     iota and eta.  Some information is partially present but
     scattered across multiple sections.
-	**Hard to locate concepts in the document.** For example, there is
     no subject index where the reader could look up unification.  The
     HTML search box is not very helpful. (You can't see the
     matching text for each search result without clicking on the
     link.  Clicking on the link takes you to the top of the section
     rather than to the matching text.)
-	**Lack of task-oriented guidance.** For example, there are more
     than 100 tactics.  What are the basic tactics that every user
     should know?  Which ones are no longer preferred?  What are the
     merits of using traditional tactics versus SSR?  How do common
     proof techniques and concepts map into Coq?  What's the best
     way to set up files for a large project or to work with libraries
     not in the Coq distribution?
-	**User-level and developer-level material are not well
     distinguished.**
-	**Style.** Inconsistency in the level of detail, assuming too much
     background, overly complex language (e.g. wording reminiscent of
     academic papers), unclear wording and non-idiomatic English.

Other areas for improvement include:
-	**Examples.** There should be many more examples, edited to be as
     brief and focused as possible (and therefore easily understood),
     starting with basic constructs of terms, ltac and tactics.
-	**Better introductions.** Many chapter and sections lack effective
     introductions.  Introductions should briefly give enough
     information so the reader can decide whether to read what
     follows.  They should describe what's in the section, what
     it's useful for and relate it to other topics.
-	**Split HTML into more and shorter pages.** The current webpages
     are so long it's easy to lose context or wander into unrelated
     material.

# Working Outline

See *\<link to PR>.* The outline is subject to revision as the project
proceeds.

# Process

We propose evolving the documentation with a series of PRs that are
small enough to be reviewed and revised efficiently.  We plan to merge
these directly into master.  (The earlier conversion of documentation
to Sphinx was done on a branch, which lead to tedious and error-prone
rework to merge the branch into master.)

The project drivers will coordinate and track tasks based on these
considerations:
-	**Prioritize by user benefit.** Do the changes that will benefit
     users the most first.
-	**Avoid merge conflicts.** Moving sections between chapters while
     someone else is editing the section is counterproductive.
-	**Availability of writers and reviewers.**
-	**Conceptual dependencies.** The work may go more smoothly if
     documentation for more-basic parts of the system are done first.

The working outline has been submitted as a Coq PR under the doc
directory.  We'll use this outline to track the progress of the
project and who's doing what.  As we begin working on each chapter
and section, we'll begin by reviewing the current chapter in a PR
to identify what changes are needed, followed shortly afterward by
creating and reviewing a revised chapter or section outline.

This success of this project will depend on help from many others with
writing and reviewing updated documentation.  There will also be many
technical details to get right and questions to answer that will need
help from those who are most knowledgeable.  In some cases we may pair
a good writer with a subject expert to write or update some sections.
We will also consider providing with copy editing assistance beyond
what can reasonably be done as part of a review.

We are currently in the process of updating all the syntax in the
document to make it match the code.  Some of the syntax was very
inaccurate.  We're doing this using a semi-automated tool to do
this (see https://github.com/coq/coq/pull/9884).
https://github.com/coq/coq/pull/10614, for example, updates the
"Terms" section of the Gallina chapter.

# Disadvantages



# Leftover thoughts:
Make Sphinx menu work better (shouldn't scroll when the main panel
scrolls)?

Create a style guide?
