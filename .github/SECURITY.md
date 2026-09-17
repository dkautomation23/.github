# Reporting a security issue

Email **hello@dkautomation.dev**. Please do not open a public issue for anything
that lets someone read data they should not.

I read reports within two working days and tell you what I intend to do. If it is
real, you get the fix and the release that carries it; if it is not, you get the
reasoning rather than silence.

## What counts here

These are command-line tools and small services that people point at their own
data. The things worth reporting:

- **A secret that escapes.** Anything that writes a credential, token or signing
  secret to disk, to a log, to a report or to the network. Redaction that can be
  bypassed belongs in this category.
- **Data crossing a boundary it should not.** A tool reading a path outside what
  it was given, or sending data anywhere other than the target you named.
- **A guardrail that does not hold.** In `mcp-data-server` that means the table
  allowlist, PII masking, row caps or the read-only barrier; in
  `webhook-rewind` it means signature handling.
- **Code execution from input.** A payload, CSV, image or document that makes a
  tool run something.

## What does not

- A tool doing exactly what its README says, where you disagree with the default.
  Open a normal issue instead.
- Findings from a scanner with no working path to abuse.
- Dependency advisories that the code cannot reach. Say which call path reaches
  it and it becomes the first list.
- Anything requiring an attacker who already has your shell.

## Supported versions

The latest release of each tool. These are small enough that a fix is a new
release rather than a backport.
