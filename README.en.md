# Proof Protocol

A protocol for AI assistants (and for people) to handle **diagnosis of complex problems**, **ticket closure** and **reverse engineering / software development** with one simple rule:

> **No proof, no advance. No counter-proof, no closure.**

*Status: draft 0.2.* · **Português:** [README.md](README.md)

> **Important notice**
>
> Every company, server, domain, account and scenario name in these files is **fictional** and used only as an example. No real organization or personal data is included.
> The assistant learns your environment **from the protocol and from the operator**: nothing advances and nothing closes until the operator sends the output of the **proof** and of the **counter-proof**. Proof + counter-proof = truth established under the tested conditions.

## The problem it solves

In complex problems, the most expensive mistake is treating a claim as truth: the system says "service running", the assistant concludes by guesswork, the ticket closes without the cause. The protocol replaces that with **gates**: the case only advances when the proof for the previous gate exists.

## How the method was born

It was born from a real mistake: an operator and an AI assistant were both fooled by a deduction that was never tested. A test run on a path different from the real failure path seemed to prove one thing, but the cause was in another layer, hidden by a generic error message. The deduction was treated as truth without counter-proof.

From that lesson came the foundations of the method: test only on the exact failure trail, in the same context; an operator's request requires an objective test; escalation levels (N1, N2, N3); a registry of masking mechanisms; and an executable rollback before changing anything.

The core idea is not to "raise the hit rate". It is to **prevent a wrong hypothesis from being closed as truth before paying the price of counter-proof**, and to make truth rest on proof, not on whoever states it: the system, the operator or the AI.

The case is described generically: no organization, system or person is identified.

*Authorship: KaLeK, with an AI assistant's help in the writing and refinements.*

## What is here

| File | What it is |
|---|---|
| `PROOF-PROTOCOL.md` | The full protocol (the file you paste into the assistant's instructions) |
| `environment-profile.example.md` | **Fictional** template of an environment profile |
| `README.en.md` | This file |
| `PROTOCOLO-DE-PROVA.md`, `perfil-ambiente.exemplo.md`, `README.md` | Portuguese originals |

## How to use

1. Paste the contents of `PROOF-PROTOCOL.md` into your assistant's instructions (project, system prompt, `CLAUDE.md`, `AGENTS.md` or equivalent).
2. Start the problem as usual. The assistant will ask for the **context** (where it runs, shell, user, privilege, read or change) and only advance once it has the requested evidence.
3. Run the commands **yourself** and return the **complete** output. The assistant does not run anything in production.
4. Close the case with the formal note. The status is only RESOLVED with a proven cause and counter-proof.

## How it learns your environment

The protocol carries no environment data. The assistant learns **from you**: it asks for what is missing, tags each fact as `[declared]` or `[proven]` and, if the platform has memory or files, **proposes** saving a local profile (see `environment-profile.example.md`). You approve what goes in. Without memory, you paste the profile at the start of the session.

**Never** put passwords, tokens or keys in the profile or in the evidence.

## What it does not do

- It does not run commands in production.
- It does not replace authorization, your organization's policy or technical judgment.
- It does not guarantee results: an AI assistant can be wrong, which is why counter-proof, rollback and the Lab Gate exist.
- It does not claim to be "the best". It is a method; its usefulness should be measured in real cases.

## Contributing

Suggestions for new **masking mechanisms** (real misleading behaviors, with proof) are welcome. Do not include any organization's data.

## License

MIT (see the `LICENSE` file). Authorship: KaLeK.
