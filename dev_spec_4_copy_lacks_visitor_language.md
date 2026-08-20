# Copy lacks visitor language — dev spec
Site: example.com · Priority 4 · Medium · Effort: Low (0.5-2 days)

## Problem
The page copy is technical and generic, not written in terms a typical visitor would use to describe their need or the solution.

## Evidence (from the live site)
> This domain is for use in documentation examples without needing permission.

## Current state
h1: This domain is for use in documentation examples without needing permission.; cta: Learn more; notes: Copy is technical and generic.

## Required change
h1: Headline mirroring customer search phrases and pain points; cta: Specific CTA; notes: Rewrite supporting copy to be instantly recognizable.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Rewrite supporting copy to be instantly recognizable.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_copy_lacks_visitor_language` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
