
- Include the previously unpublished host improvements: isolated provider sign-in and model selection, local image analysis and WebP support, consent-gated image AI, and controlled rename extensions. Plugins retain independent releases.
- Keep enabled, eligible Finder plugin menus persistent until state changes; remove menu expiry and renewal timers. Reconcile on startup, wake and host activation without making visibility depend on those events.
- Separate persistent menu schema v4 from unchanged 30-second invocation requests (v3). Read legacy v3 menu snapshots, including expired ones, as display hints only. Package, permission, entitlement and file checks still run before execution.
- Cover persistent storage, stopped hosts, state changes, legacy migration and stale-menu authorization rejection. Preserve native Settings appearance and core actions.

