
- Combine declared plugin access and AI data disclosure in one initial confirmation using generic `aiDisclosureCategories`. Denial adds no grants; turning access off revokes disclosure consent. Update descriptions in seven languages.
- Include optional BETA badges in plugin lists and detail headers, and bounded, explicitly authorized `files.readBytes` for current selections. Remote AI still requires selected-file-content disclosure.

- Preserve accumulated per-plugin/provider data disclosure grants when additional categories are approved, preventing repeated prompts caused by overwriting earlier grants. Revocation still clears all grants; no new category is auto-approved.
- Localize original filename disclosure and add persistent-store regression checks for accumulated consent, reload, isolation and revocation.

