# 1. Annotate the original plan rather than publish a rewritten itinerary

Date: 2026-08-17

## Status

Accepted

## Context

The first version of `public/itinerary.html` was a rewritten itinerary. It was
researched carefully against primary sources, but it silently disagreed with the
group's own Google Sheet on three whole days:

- Monday evening: the sheet says Ortisei, the document said Bolzano old town.
- Wednesday: the sheet says Lago di Braies at 14:00–18:00, the document moved it
  to before 09:00 and rewrote the morning.
- Friday and Saturday: the sheet says islands both days, the document assigned
  Friday to the historic centre — and then listed "spending both Friday and
  Saturday on the islands" in its own Mistakes section.

Nowhere did it say it had changed anything. A reader holding the sheet could not
tell which differences were corrections and which were the author's taste.

The document's actual purpose is not to be the plan. It is to be reviewed by six
people against a plan they already wrote, so they can decide what to change. Its
readers are the authors of the thing it comments on.

## Decision

The **Original plan** is the spine. The document reproduces the group's own
Block labels verbatim — in their wording and language, including the Vietnamese
ones — and attaches Annotations to them. It never renumbers, reorders or
silently substitutes a Block.

Content that cannot be attached to a Block is either moved to a short reference
appendix, or cut.

Disagreements are expressed as Annotations carrying a Marker, never as a
rewritten Block. Where two defensible versions exist, the Marker is *Open* and
both are costed; the document does not pick for the group.

## Consequences

The document becomes navigable by anyone holding the sheet, and every
disagreement becomes explicit and attributable. Review can happen Block by
Block.

It also constrains us. We inherit the sheet's shape, including its
inconsistencies — Monday's blocks span three hours while Tuesday's span one, and
Friday and Saturday are a single ten-hour Block each with no internal detail.
Rich content has nowhere to hang on those two days, so Venice detail lives in
the appendix and is cross-referenced rather than scheduled.

It means the document goes stale when the sheet changes. That is acceptable: it
is a review artefact for one round of decisions, not a living itinerary.

The alternative considered was a rewritten itinerary with a "what changed" box
per day. Rejected because it puts the disagreements in a summary the reader
skims, rather than at the exact Block the reader is arguing about.
