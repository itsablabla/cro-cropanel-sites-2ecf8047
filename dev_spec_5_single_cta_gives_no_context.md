# Single CTA gives no context — dev spec
Site: example.com · Priority 5 · Medium · Effort: Low (0.5-2 days)

## Problem
The only call to action, 'Learn more', provides no indication of what will be learned or why it matters, failing to reinforce any message about the offering.

## Evidence (from the live site)
> (see report)

## Current state
h1: Clear value proposition; cta: Learn more; notes: CTA is vague and lacks context.

## Required change
h1: Clear value proposition; cta: Specific CTA naming product or outcome; notes: Change CTA label to be specific about next step and value.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Change CTA label to be specific about next step and value.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_single_cta_gives_no_context` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
