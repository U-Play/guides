Project management process with Trello
======================================

The project management process with [Trello](http://trello.com) spans three
boards:

* Product Design
* Bugs & Refactoring
* Current Week

![Planning](http://f.cl.ly/items/3t433z2z341w1o0a1q0s/Screen%20Shot%202012-12-02%20at%2010.02.29%20AM.png)

The goal of the Product Design board is to keep the team aligned on the vision
and solving defined problems.

The goal of the Bugs & Refactoring board is to keep track of bugs and
refactorings that are out of scope for the current week.

Cards from Product Design and Bugs & Engineering boards are pulled into the
Next Up list on the Current board as described in the "Weekly Planning Meeting"
section below.

The Next Up list is the single prioritized list that the product team
(designers and developers) refer to in order to know what to work on next.

Trello cards
------------

A card represents a single user experience, bug fix, or engineering task.

Cards start out as a simple idea, 1-2 sentences long. As they are pulled through
boards, detail is added, explaining why (from a business perspective)
we're focusing on it, and maybe notes on suggested implementation (though
designers and developers may take or leave it at their discretion; it's supposed
to be helpful, not prescriptive).

Product Roadmap
---------------

The cards in this list are the major projects to be completed. In agile terms,
they are called "epics." They are not directly moved to other lists but do
inform cards in User Experience and Engineering lists.

Bug Fixes
---------

The cards in this list are bugs in the described state.

If a bug is labeled Critical, then it is pulled immediately into Next Up. If the
bug is not critical, it stays in Bug Fixes until the next planning meeting.

A bug has steps to reproduce the bug and optionally a screencast.

User Experience
---------------

The cards in these lists are user experience enhancements. They should primarily
be sourced from actual users.

Engineering
-----------

The cards in these lists are refactorings and other engineering tasks necessary
to fix bugs or improve the user experience.

If an engineering task is labeled Critical, then it is pulled immediately to
Next Up. If the task is not critical, it stays in Engineering until the next
planning meeting.

Weekly Planning Meeting (1-2 hrs)
---------------------------------

We have one meeting each week. It is all-hands and designed to ensure everyone
knows what's going on with the product and to celebrate the work of team
members. The advisor runs this meeting like this:

* We start by reviewing the cards that went live last week, taking 30 seconds
  to describe each card, and congratulate those who worked on them, showing
  their avatar.
* We then review the Product Roadmap list. The advisor shows the current state
  of the roadmap and provides insight into what these cards are and why
  they're a priority (the business case).
* We then review the User Experience list, pulling what we estimate to be an
  appropriate amount for this week into Next Up.
* We then re-sort the entire Next Up queue according to priority. Cards that
  were at the top of the list last week may be moved to the bottom.
* We then review the Bugs list. We pull any important bugs into Next Up and
  prioritize then at the top of the queue before everything else. We want to
  always be fixing what's broken first.
* We then review the Engineering list. We pull cards into Next Up based on what
  the designers and developers believe is appropriate given the previously
  stated Product Roadmap background and current Bugs.

Building and Shipping
---------------------

![Shipping](http://f.cl.ly/items/2h2d2Z1z0X3s0n3d3y0R/Screen%20Shot%202012-12-02%20at%2010.03.44%20AM.png)

The cards in the Next Up list are prioritized, vetted, and ready for design &
development. A designer or developer "puts their face on it" by assigning it to
themselves and pulling it into the In Progress list.

Designers and developers may pull any card out of Next Up that they feel they
can handle, but should consider the cards are prioritized by importance.

The cards in the In Progress list are actively being designed or developed.
Etiquette is that you should never have your face on more than two cards at a
time. Work is done in a
[feature branch](https://github.com/thoughtbot/guides/tree/master/protocol).

When a designer or developer creates a pull request for their feature branch,
they move the card to the Code Review list. Any reviewers "put their face on it"
while reviewing.

There is no central chokepoint for merging into master: everyone can do it.

The cards in the Testing on Staging (or Testing on Ad Hoc build for iPhone apps)
list are deployed to staging (or distributed via TestFlight for iPhone apps).
The card creator and a designer review it for accuracy and user experience.

There is no central chokepoint for deploying to staging: everyone can do it.

The cards in the Ready for Production list include cards that have been accepted
on staging and are ready to be deployed (but not necessarily rolled out).

There is no central chokepoint for releasing to production: everyone can do it.

The cards in the Live (Week [date]) lists have been released. Each week has its
own Live list so we can follow what got released when.
