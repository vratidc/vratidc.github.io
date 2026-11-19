# Adding or closing an opening

Files starting with `_` are not published, so this note stays private.

Each `.md` file in this folder is one opening. The Openings page (`/openings`)
lists them automatically, sorted by apply-by date (earliest first). Nothing
needs to be edited on that page.

## Add an opening
1. Copy an existing file (e.g. `vr-designer.md`) and rename it.
2. Change `title`, `description`, `permalink`, and the fields below.
   Keep every field; leave a value empty if it doesn't apply.
3. Write the description (lede, Role Overview, Eligibility, Desired
   Qualifications) under the front matter, as in the other files.

## Close an opening
Set `open: false`. It moves to "Past Openings" and its page shows
"Applications closed". It also closes on its own the day after `apply_by`.

## Fields
| Field | Meaning |
|---|---|
| `status` | Status label: `accepting`, `shortlisting`, `interviews`, `interviewed`, `closed` or `filled`. Empty = automatic: Accepting applications while open, Shortlisting in progress once the deadline passes, Applications closed if `open: false` |
| `open` | `true` = current opening, `false` = past |
| `icon` | Card icon: `3d`, `vr` or `design` |
| `tag` | Label above the title, on the card and the opening's page |
| `facts:` | Quick facts, shown in the order the lines are written. Empty ones are hidden. Mentor shows only on the opening's page, not the card |
| `facts: mentor` | e.g. `Prof. Jayesh S. Pillai` |
| `facts: duration` | e.g. `Jan – Jun 2027` |
| `facts: stipend` | e.g. `Paid` or `₹15,000/mo` |
| `facts: location` | e.g. `In-person (IIT Bombay)` |
| `facts: apply_by` | Deadline as `DD-MM-YYYY`. Shown as e.g. "Nov 20, 2026" |
| `card_stipend` | Stipend wording on the card, if different (e.g. `Paid stipend`) |
| `require_portfolio` | `true` shows the "Required: resume and portfolio" box |
| `apply_email` | Where applications go; empty = hello@imxd.in |
| `apply_subject` | Email subject. Empty = no "Apply via Email" button (e.g. IRCC openings) |
| `apply_cc` | Optional CC address for the apply email |
