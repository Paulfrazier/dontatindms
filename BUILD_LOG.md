# Build Log — Don't @ in DMs.

> Append an entry whenever you change this site. Newest first.

## 2026-10-06 — Make "even if they haven't joined the thread" explicit up front

**Prompt:** update the site to make it clear from the start even when the thread doesn't have the other person yet. double check true.

**Problem:** The intro said 1:1 DMs notify on thread replies, but never said this holds even when the other person hasn't started, replied to or been mentioned in the thread. That participation rule is what makes group DMs different, so readers could carry it over to 1:1 threads.

**Solution:** Spelled out the 1:1 "all threads" rule in the thesis, the first explainer card, the meta description and the first takeaway. Rewrote the 1:1 "old message" scenario to test the exact case: a thread under your own message that the other person hasn't replied in.

**Key decisions:**
- Re-verified against [Slack: Use threads](https://slack.com/help/articles/115000769927-Use-threads-to-organize-discussions-) on 2026-10-06. It says "By default, you'll be notified of new replies to all threads in one-to-one DMs," with no participation condition. The "started, replied, or mentioned" rule applies only to channels and multi-person DMs.
- Edited an existing scenario instead of adding one, so the bank stays at 40 (30 `plain` / 10 `at`) and the "40-scenario" copy stays true.
- Also live as of today: DNS (`A dontatindms → 76.76.21.21`) added via the Namecheap API, and the Vercel certificate issued after re-attaching the domain to the project.

**Changed files:** `spec.json`, `index.html`, `BUILD_LOG.md`

## 2026-10-03 — Initial build

**Prompt:** /fairpoint don't @someone in a dm. even in a thread. they get the notif! (confirm via slack docs this is true true, and link to it)

**Problem:** People @mention the other person in Slack DMs (and DM threads) "to be safe", but DMs already notify by default and 1:1 DM thread replies notify both people. The @ is redundant and reads as impatient.

**Solution:** Scaffolded from `fairpoint-kit/template.html` (Playful Arcade design system)
with a site spec injected into `#site-config`. 40 scenarios across choices
`plain` (30) / `at` (10).

**Key decisions:**
- Subdomain: `dontatindms.fairpoint.website`
- Claim verified against Slack Help Center before writing: [Use threads](https://slack.com/help/articles/115000769927-Use-threads-to-organize-discussions-) ("By default, you'll be notified of new replies to all threads in one-to-one DMs"), [Guide to notifications](https://slack.com/help/articles/360025446073-Guide-to-Slack-notifications), [Use mentions](https://slack.com/help/articles/205240127-Use-mentions-in-Slack) (non-members aren't notified), [Do Not Disturb](https://slack.com/help/articles/214908388-Pause-notifications-with-Do-Not-Disturb) (once-a-day DM override). Sources are linked in the explainer, trap and takeaways.
- Legit @ cases scoped to what the docs support: group-DM threads where the person hasn't started/replied/been mentioned, assigning ownership in a group DM, and a non-pinging reference to someone outside the DM.
- Two choices (no @ vs @). A third "use their name" option was dropped as too fuzzy to grade.

- Design review: PASS 8.8/10 on the first round. Applied fixes at site level, leaving the shared template untouched: links styled with `--purple-electric` inline, coral accents swapped to `--purple` for AA contrast, fixed a misquoted Slack setting name, softened two unverified claims, and rebalanced the answers from 33/7 to 30/10 so always choosing "no @" scores lower.
- Deployed to Vercel project `dontatindms`. DNS: `A dontatindms → 76.76.21.21` must be added in Namecheap by hand, because the API rejected this machine's IP.
- Linked from the fairpoint.website hub (13 lessons).

**Changed files:** `spec.json`, `index.html`, `CONTRIBUTING.md`, `BUILD_LOG.md`
