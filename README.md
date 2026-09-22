### Deterministic tools for working with AI agents

I build the parts of an AI workflow that have to be right every time, such as
arithmetic, state and audits. Those go in small, tested, deterministic code.
The language model gets the parts it is good at: gathering context, naming
assumptions, and explaining results.

---

#### [cashflow-engine](https://github.com/jamejialicona-cmyk/cashflow-engine)

A project cash flow engine in pure TypeScript. Give it a contract and it
returns a month-by-month schedule plus IRR, NPV, payback, working capital,
break-even and sensitivity analysis. No I/O and no framework. Every rate,
price and cost is an input. It replaces the spreadsheet model, which cannot
be tested or diffed.

`TypeScript` · `financial modeling` · CI on Node 20 and 22

#### [cashflow-mcp-server](https://github.com/jamejialicona-cmyk/cashflow-mcp-server)

The engine exposed as tools an agent can call over the Model Context Protocol.
The model gathers the terms of the deal, the engine does the math, and the
model explains the result. Every tool is a pure, idempotent computation that
returns its full schedule, so any answer can be re-run and audited.

`MCP` · `TypeScript` · `agents` · smoke test for every tool over stdio

#### [vault-starter](https://github.com/jamejialicona-cmyk/vault-starter)

A method for running projects that last months with an AI agent. The project's
knowledge lives in a versioned Markdown vault instead of chat history, and the
cost of opening each session is measured, not guessed. The repo includes
the method, a startup-cost auditor, and three Claude Code skills. The method
was distilled from two long deployments in unrelated domains.

`Python` · `Claude Code` · `context engineering` · CI on Linux and Windows

---

#### How I work

- **Arithmetic belongs in code.** A model can explain a number. Code should
  compute it.
- **A green test is not a measurement.** My test suites include control cases:
  defects built on purpose to prove the checks can fail.
- **A fix goes to the source of the data,** not to the line the report
  points at.
