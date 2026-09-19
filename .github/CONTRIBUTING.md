# Contributing

The default guide for repositories under
[github.com/dkautomation23](https://github.com/dkautomation23). Where a
repository has its own `CONTRIBUTING.md`, that one wins — it names the real
build and test commands for that stack.

## Before you write code

Open an issue first if the change is more than a fix. Not for ceremony: most of
these tools deliberately do *not* do certain things, and the README says which.
A pull request that adds one of them will be declined, and I would rather you
found that out in a comment than after an evening of work.

A fix with a failing test attached needs no issue. Send it.

## The one rule that is not negotiable

**A new check starts as a failing test.** Write the test, watch it fail for the
right reason, then make it pass. Every tool here reports on someone else's
data, and a check that was never seen to fail is a check nobody has verified.

## What CI runs

Every repository builds and tests on a clean machine on every push. The
workflow file in `.github/workflows/ci.yml` is the source of truth for the
commands — not this page, and not the README.

Before you open a pull request:

- run the tests the way CI runs them, in a clean environment. For Python, a
  fresh virtual environment per repository; a shared one hides a missing
  dependency until CI finds it;
- keep runtime dependencies at zero unless there is no reasonable alternative.
  Most of these tools ship with none on purpose;
- do not commit generated output, lockfile churn unrelated to your change, or
  credentials in a test fixture. Use obvious dummies.

## Commit messages

Look at `git log` in the repository and match it. In short: a short sentence
saying what changed for the user, then a blank line, then why — the reason the
diff cannot show. No ticket prefixes, no emoji.

## What happens to your pull request

I read it within a few days. I will either merge it, ask a question, or explain
why it does not fit. A change that is right but out of scope for the tool gets
that answer plainly rather than sitting open for months.

## Licence

By contributing you agree your work is published under the repository's licence
(MIT unless the repository says otherwise).
