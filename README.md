# bs-a11y-keyboard-fixtures

Test fixture pages for the KeyboardAT regression suite (release-6.4.0-WA flow).

These mirror `browserstack/bs-a11y-checks/assistedTests/keyboard/` so the
regression suite can hit live URLs while the upstream PR
([browserstack/bs-a11y-checks#174](https://github.com/browserstack/bs-a11y-checks/pull/174))
is pending merge.

## Pages

| Page | What it exercises |
|---|---|
| `custom_elements.html` | Non-semantic interactive divs (4 sections: plain, ambiguous trap, mouse-only role=button, scoped region) |
| `dropdown_unreachable_manual.html` | 6 elements / 4 dropdowns (2 reachable + 2 unreachable) for the per-element manual review flow |
| `navigation_shield_dropdowns.html` | 4 sections: aria-controls + nav, aria-controls + scroll-only, anchor href, submit button |
| `dropdown_phase2_unrecoverable.html` | 3 sections: aria-activedescendant focus loop, modal trap, generic Tab preventDefault trap |
| `shadow_dom_dropdowns.html` | Open shadow root (engine should detect) + closed shadow root (engine should NOT detect) |
| `no_custom_or_dropdowns.html` | Semantic-only — drives both empty-state code paths (COLLECT skip + zero-dropdown) |
| `large_custom_elements.html` | 300-tile grid — guards the WebSocket-stall regression for large payloads |

## Once merged upstream

Switch the regression suite's fixture URLs back to
`browserstack.github.io/bs-a11y-checks/...` and archive this repo.
