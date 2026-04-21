# Review Guidelines - Adversarial Review

## Think like an attacker / QA engineer trying to break this code

For every change in the diff, ask:
1. "What is the worst thing that could happen if this code runs?"
2. "What input would make this fail?"
3. "What happens if this runs concurrently with itself?"
4. "What happens if the external dependency (API, DB, cache) fails here?"

## Specific attack vectors to check:
- Can a user craft input to bypass validation?
- Can race conditions cause data corruption?
- Can error paths leave resources leaked or state inconsistent?
- Can cache entries collide and return wrong data?
- Can integer overflow, off-by-one, or type coercion cause wrong results?

## Report aggressively
If you can construct a plausible scenario where the code fails, report it. Include the specific trigger path. The validator will filter false positives -- your job is maximum coverage.
