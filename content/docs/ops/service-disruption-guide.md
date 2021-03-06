---
menu:
  docs:
    parent: policies
layout: ops
title: Service disruption guide
---

This guide outlines how we handle communications for service disruptions during East Coast business hours.

Not a guide for:

* Hours outside of East Coast business hours -- out of scope for this document.
* Security incidents -- switch to [security incident guide]({{< relref "docs/ops/security-ir.md" >}}).
* Major service disruptions (more than 30 minutes of unexpected downtime or significantly reduced service) -- switch to [contingency plan]({{< relref "docs/ops/contingency-plan.md" >}}).

## Threshold for "service disruption"

**If there is an unexpected user-impacting problem that we believe is a platform problem.** 

Examples:

* We caused end-user-visible errors in customer applications.
* A platform-owned component such as the dashboard or brokers is giving errors.
* Two or more teams using cloud.gov have reported the same non-trivial problem, which indicates it isn't just a problem with a customer application.
* AWS or another service we depend on is causing problems for our users.
* Something unexpected went wrong during scheduled maintenance, and it impacts users.

## How soon to post to Status Page

As soon as possible. Goal: at most 15 minutes after the first cloud.gov team member notices the problem.

## Who is responsible for posting and updating

* First person on the cloud.gov team who notices a problem is responsible for finding the right people to address it (can include themself), including finding a person with Status Page access to post about it (can include themself).
* Platform squad person on support rotation should be the first person to begin addressing the technical issue (and the first person for non-platform squad people to ping for help with this). See the platform squad channel topic for the current person.
* A person should explicitly say “I'm taking care of Status Page for this” and continue being responsible for updates until they explicitly hand off that responsibility.

### Drafting and approval

* **If you're platform squad:** Draft and ping for comms help (Bret, Britta), but if they aren’t available within 5 minutes, just post it.
* **If you're not:** Draft and ask platform squad for technical check before posting.

[We have some templates and drafting space in this doc.](https://docs.google.com/document/d/1paDOxlB7GFItrEJ9pqPExApiAd4GeB_SpGR6Ronf4Lw/edit)

### Updates

* If you're writing an update to a post about a new related problem, also update the post summary (the subject line) to make it summarize the whole event.

## When to close

We close the event when **we believe the disruption is no longer affecting customers**.

The person with Status Page responsibility is responsible for asking “any objections to closing it?” and closing it if none.

* It's helpful but not required to write something that’s informative about the resolution as a closing message.

A postmortem is not necessary to close, and it does not have to happen immediately after closing.

## Ensure a postmortem happens

The person who closes the event should then put a card on the component-owning squad’s board in the urgent lane about writing and posting a postmortem.

For non-security-sensitive work, work to resolve root causes does not have to be completely done before we post the postmortem.
