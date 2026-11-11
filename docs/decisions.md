# Architecture Decision Log

Short records of *why* we chose what we chose. Newest first.

## 2026-11-11 — PHP + MySQL instead of React + Supabase

**Reason:** Shared hosting in Kenya is cheap and widely available.
Ward-level budgets can support KES 500–2,000/month hosting. A React SPA +
Supabase stack requires a build pipeline and a paid backend tier.

**Trade-off:** We implement auth, RLS-equivalent role scoping, and audit
logging ourselves. These must be tested, not assumed.

## 2026-11-11 — No resident login in v1

**Reason:** Residents only need to (a) register, (b) submit requests, and
(c) track a request. All three work without an account. Tracking is by
reference number + phone.

**Deferred:** OTP login via SMS (Africa's Talking) is a v2 feature.