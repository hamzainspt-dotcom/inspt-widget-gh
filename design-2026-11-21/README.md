# INSPT widget design — 21 November 2026

Design mockups for a single, consistent look across all nine INSPT widgets.
Open `index.html` for the set.

**These are mockups, not working widgets.** They carry sample figures and invented names only —
no real customer, agent or policy data. Nothing here is wired to Zoho, and none of the live
widgets in the repository root have been changed.

## The rule
Decoration is INSPT brown. Green and red are not decoration: they carry meaning and do not change.

| | | |
|---|---|---|
| `#412a16` | dark | fills, primary buttons, the lead figure block |
| `#804a1c` | accent | the INSPT theme brown |
| `#a9743a` | mid tone | second step of the ramp |
| `#ddc9b0` | light tone | chart bars, third step |
| `#23634e` | **money in** | paid, received, a check that passed |
| `#ab3225` | **money out** | overdue, owed, a check that failed |
| `#8a6000` | **warning** | needs attention |

Two colours were moved away from the values the design arrived with, because measured against the
INSPT accent they were not separable: the original warning tone sat only ΔE 7.3 (CIELAB) from
`#804a1c`, which is the same colour to the eye, and the original "money out" tone was a brown-red
at ΔE 20.2. The replacements sit at ΔE 19.3 and 29.5. Every text colour passes WCAG AA on white;
the weakest is the warning at 5.59:1.

## Files
- `inspt-widget.css` — the shared stylesheet: tokens, components, and the Geist webfont embedded,
  so a widget makes no outside font request. Lato is the fallback, which is what Zoho's own
  reports use.
- Four recoloured screens: `executive-dashboard`, `agent-statement`, `policy-upload`, `employee-home`.
  These still carry their own copy of the tokens inline; folding them onto `inspt-widget.css` is
  part of the real build.
- Five new screens: `insurer-statement`, `reconciliation-health`, `renewals-command-center`,
  `ms-entries-viewer`, `staff-policy-viewer`.

## Not done
Applying any of this to the real widgets. That is a separate job, one widget at a time, each as a
new file, with the Zoho app exported first and the widget URL switched only on Hamza's word.
