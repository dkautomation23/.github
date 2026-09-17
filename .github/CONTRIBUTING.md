# Contributing

These tools are small on purpose. A change is easier to accept when it keeps
them that way.

## Before you write code

Open an issue first if the change adds a flag, changes output, or touches
anything in the README's **Honest limits** section. That list is not a to-do
list — each entry is a decision with a reason, and the reason is usually that
the alternative is a guess. Arguing against the reason is welcome; a pull
request that quietly removes it is not.

Typos, broken links, a wrong number in a README: just send the fix.

## Running it

Every repository runs on a clean machine with one command and no service to
start.

```bash
# Rust
cargo test && cargo clippy --all-targets -- -D warnings

# Python, single-file tools
python <tool>.py --selftest

# Python packages
pip install -r requirements.txt && python -m pytest -q

# TypeScript
npm install && npm test
```

CI runs the same commands on a clean runner. If it is green locally and red
there, the difference is almost always a dependency that exists on your machine
and is missing from `requirements.txt` or `package.json` — that is a real bug and
worth its own fix.

## What a good change looks like

- **It comes with the check that fails without it.** One assertion in the
  existing `--selftest`, one `#[test]`, or one `it(...)`. No new framework.
- **It says what it costs.** New dependency, slower run, more memory, a case
  that now behaves differently — in the pull request description, not discovered
  later.
- **It leaves the honesty intact.** If the change makes a documented limit
  obsolete, update that section in the same commit.
- **The commit message explains why.** What changed is in the diff; why it
  changed is not, and that is the part someone needs in a year.

## Style

Match the file you are editing. Comments explain the reasoning behind a decision,
not what the line does — the code already says that. British or American
spelling, whichever the file already uses; consistency inside a file beats
consistency across the repository.

## Licence

Contributions are under the MIT licence of the repository you are contributing to.
