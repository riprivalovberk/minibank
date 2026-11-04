# minibank

A tiny bank service that orch's agents work on. No web framework: a handler takes a
`Request` and returns a `Response` (`minibank/http.py`).

- `minibank/ledger.py`: accounts and balances, always `Decimal`
- `minibank/api/`: HTTP handlers (`accounts.py`)
- `minibank/payments/`: card payments. Protected: only `payments_developer` may change it,
  and every change needs a security review (orch rule PAY-001)
- `tests/`: pytest

Run the tests with `python -m pytest`.

To have orch's agents work on it, make an orch project whose target repo folder is this
one (`orch ui` → **+ New** → Target repo folder). Approved changes merge into this repo's
`main`. For a throwaway copy, `git clone` this folder somewhere else and point orch there.
