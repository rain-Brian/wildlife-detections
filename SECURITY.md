# Security and privacy

This repository publishes static pages and media. It runs no server, accepts no user input,
stores no accounts, and sets no cookies. The review controls on a report page keep their state
in your own browser and send nothing anywhere.

## Reporting something

Please report privately rather than opening a public issue, particularly for the first two
categories below.

Use GitHub's private vulnerability reporting on this repository, or contact the maintainer
directly.

**Report privately if you find:**

- **A credential, key, token or connection string** anywhere in a published page, manifest or
  asset. Publishing runs an automated scan for these, but a scan catches the patterns it
  knows about.
- **Infrastructure detail**: a hostname, storage account, key vault, subscription identifier,
  systemd unit or internal path. None of it belongs here and its presence is a defect in the
  publishing gate, not just in one page.
- **Personal information** in a frame or clip. These feeds point at wildlife, but the Mount
  Rainier cameras are public-facing and a person can walk through shot. If you find an
  identifiable individual in published media, say so and it will be removed.

**Also worth reporting:** media used without the right to publish it, or a credit that
misstates who owns a feed. See `NOTICE` for the current position.

## Response

Reports are acknowledged as quickly as I can manage; this is a personal project and not a
staffed service. Anything in the three categories above is treated as urgent, and the usual
first action is to unpublish the affected report while it is investigated rather than to
debate whether it qualifies.
