# Review checklist

Use this checklist before promoting any candidate from local review into the public repo.

## Source quality

- Is the upstream repo understandable within a few minutes?
- Is the scope clear?
- Does it look maintained enough to be worth reviewing?
- Is it solving a real problem instead of doing AI word salad?

## Safety

- Any suspicious scripts?
- Any binaries or opaque payloads?
- Any credential harvesting, wallet, trading, proxy abuse, or stealth behavior?
- Any hidden write behavior or destructive defaults?
- Any setup steps that look sketchy or over-privileged?

## Usability

- Can a normal person understand why this asset exists?
- Are the dependencies honest and realistic?
- Is it portable enough to adapt?
- Does it need trimming before public inclusion?

## Public repo fit

- Does it belong in `skills/` or `souls/`?
- Would it make the public repo better, not noisier?
- Is the public version clean and concise?
- Are local review notes kept out of the public tree?

## Publish gate

Promote only if the answer is basically yes to:
- useful
- safe enough
- understandable
- maintainable
- worth showing publicly
