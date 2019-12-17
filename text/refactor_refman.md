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
first. Existing online ressources should be enough to learn Coq, and
the reference manual should be a good complement to one of the
standard tutorials.

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
     HTML search box is not very helpful. (This is something that will
     need to be improved independently of the refactoring of the manual.)
-	**Lack of task-oriented guidance.** For example, there are more
     than 100 tactics.  What are the basic tactics that every user
     should know?  Which ones are no longer preferred?  How do common
     proof techniques and concepts map into Coq?  What's the best
     way to set up files for a large project or to work with libraries
     not in the Coq distribution?
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

# New structure

## General idea

Topics are gathered in a single place where they are explained in depth,
starting with a high level view, with lots of examples, then a more
exhaustive presentation aimed at the experts, to finish with theoretical
and implementation considerations that hint at how to improve the actual
code, what are the limitations, and how to contribute.

## Table of contents

*This outline is subject to revision as the project proceeds.*

* Introduction / How to read this manual

* Core calculus / Kernel
  — Gallina without elaboration (a checker should ideally be able to do that).
  * Summary / Highlights
  * Terms
  * Typing
  * Conversion
  * Universe Polymorphism
  * SProp
  * CoInductives
  * Native Integers
  * VM and native compute
  * Module system
  * Libraries (saving / loading)
  * Extraction (?)

* Gallina and elaboration, related vernacular commands
  * Summary / Highlights
  * Terms with holes
  * Unification (*new*)
  * Extended pattern-matching
  * Notations
  * Implicit Arguments
  * Coercions
  * Type Classes
  * Canonical Structures
  * Library management (scoping of defs, etc.)
  * Other commands

* Proof Languages
  * Summary / Highlights
  * Interactive model, proof handling
    * Parallel proof processing
  * Tactics
  * SSR
  * Other proof languages?
  * Ltac
  * Ltac2
  * Other tactic languages
    * Mtac2
  * Decision procedures / general automation
    * Omega / Micromega
    * Ring
    * Nsatz
    * Eauto
    * Generalized rewriting

* Standard library / package ecosystem

* Developing
  * Structuring projects
  * Coq commands
  * coqdoc
  * coq_makefile, Dune, making plugins
  * IDEs: coqide, proof-general, vscoq...
  * Continuous integration
  * How to review a Coq formalization
  * ...

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

As we begin working on each chapter and section of the new outline,
we'll begin by reviewing available material to identify what changes
are needed, and what writing will be required.  We will leave
placeholders asking for contributions for sections where significant
writing is needed.

This success of this project will depend on help from many others with
writing and reviewing updated documentation.  There will also be many
technical details to get right and questions to answer that will need
help from those who are most knowledgeable.  In some cases we may pair
a good writer with a subject expert to write or update some sections.
We will also consider providing with copy editing assistance beyond
what can reasonably be done as part of a review.

## Related note on grammars in the manual

We are currently in the process of updating all the syntax in the
document to make it match the code.  Some of the syntax was very
inaccurate.  We're doing this using a semi-automated tool to do
this (see https://github.com/coq/coq/pull/9884).
https://github.com/coq/coq/pull/10614, for example, updates the
"Terms" section of the Gallina chapter.

# Disadvantages

Working on refactoring the manual incrementally will create
intermediate states which can be more confusing than what we started
with.  If we end up not having finalized the refactoring towards the
end of a release cycle, we will need to make adjustments so that it
still looks good.

# Leftover thoughts:
Make Sphinx menu work better (shouldn't scroll when the main panel
scrolls)?

Create a style guide?
