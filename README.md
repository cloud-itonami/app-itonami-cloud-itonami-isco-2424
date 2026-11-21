# cloud-itonami-isco-2424
Occupation reference: ISCO-08 (International Labour Organization, 2012), code 2424. This app is not produced, reviewed or endorsed by the ILO.
職業の参照: ISCO-08（国際労働機関 ILO、2012 年）のコード 2424。日本語の名称は当方の訳です。この app は ILO が作成・確認・推奨したものではありません。

**Community Training Practice** — the ISCO-08 2424 (Training and Staff
Development Professionals) actor, an ISCO **Wave 0** occupation per
ADR-2607121000: pure-cognitive work, the LLM-first wave, no robotics
gate.

**Maturity: `:implemented`** — TrainingAdvisor ⊣ TrainingGovernor as a
langgraph StateGraph (`intake → advise → govern → decide →
commit/hold`, human-approval interrupt), modeled on
cloud-itonami-isco-4311's bookkeeping actor. 14 tests / 31 assertions
green.

The training-specific HARD invariants — all deterministic curriculum
facts, none approvable past:

1. **Curriculum basis** — every cited module must be REGISTERED and
   belong to this client (no invented curriculum).
2. **Prerequisite order** — a module's prereqs must appear earlier in
   the plan sequence (missing prereqs count too). Scheduling the
   advanced module first is a graph fact, not an opinion.
3. **Hours integrity** — `:total-hours` must equal the sum of the
   cited modules' hours (no padding).

Escalations (always human sign-off): `:send-invitations`
(external-send), low confidence (< 0.6).

AGPL-3.0-or-later, forkable by any qualified operator. Part of the
[cloud-itonami](https://itonami.cloud) open business fleet.
