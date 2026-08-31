# Working instructions: wildlife-detections

**This repository is generated. Do not edit its contents by hand.**

Everything under `reports/`, plus `index.html`, `sitemap.xml` and `NOTICE`, is written by
`reports/publish.py` and `reports/index.py` in `wildlife-inference`. A hand edit is
overwritten by the next publish, silently.

To change a report, change the builder or the run that produced it and publish again. To
change the index or a credit line, change the generator or the feed registry.

The files that *are* edited by hand: `README.md`, `METHODS.md`, `CONTRIBUTING.md`,
`SECURITY.md`, `CODE_OF_CONDUCT.md`, `CITATION.cff`, `LICENSE`, `LICENSE-CODE`.

## This repository is public

Nothing about the infrastructure belongs here: no hostnames, storage accounts, key vaults,
systemd units, subscription identifiers, SAS parameters, or operator paths. A redaction gate
enforces this at publish time, but a gate catches the patterns it knows about.

No model code, no configuration, no credentials, ever. The absence of code is what keeps
GPL-3.0 and the OrcaHello RAIL licence out of the published artifact.

## Licensing is not one answer

Original material is CC BY 4.0 and the shipped HTML/CSS/JS is MIT, but **each report carries
the licence its sources impose**, recorded in its `report.json` and computed from the feed
registry. Reports built from Orcasound audio are CC BY-NC-SA 4.0, because share-alike follows
into derived work. Never state a single site-wide content licence as though it covered the
reports.

## Media rights

Every frame, clip and spectrogram derives from a feed somebody else owns. `NOTICE` is
generated from the registry. If a feed operator asks for attribution changed or content
removed, do it first and discuss after.
