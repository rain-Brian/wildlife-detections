# Cascadia Listening Post

Wildlife detection reports from continuously monitored public feeds in the Salish Sea and at
Mount Rainier.

**Reports: https://rain-Brian.github.io/wildlife-detections/**

Hydrophones and cameras that anyone can listen to or watch are recorded around the clock,
run through detection and classification models, and turned into reports that show what was
found and how far it can be trusted. Each report keeps the evidence alongside the claim, so a
reader can listen to the call or look at the frame and disagree.

## What this repository is

Rendered reports and their media. Nothing else. No model code, no configuration, no
infrastructure detail. The systems that produce these reports live in private repositories;
this one exists so the results can be read and shared.

**These pages are generated.** Do not open a pull request against them; see CONTRIBUTING.md.

## How to read a report

Three things are true of every report here, and they are the difference between reading it
correctly and misreading it.

**Every card is a model detection, not a confirmed sighting.** Unless a card says a person
reviewed and confirmed it, a model produced it and a model can be wrong. The reports show
their false positives rather than hiding them, because a detection page that only shows
successes cannot be judged.

**Every label is shown only above its own measured error rate, at its own site.** A label is
tested against the false-positive floor measured at that specific hydrophone, not a pooled
figure across all of them. Pooled floors let a busy site license claims at a quiet one, which
is a real error this project made and corrected.

**Absence of detections is not absence of animals.** Each report states how many hours of
usable signal it covers. A day with no detections and a day with no recording look identical
on a count, and they are not the same thing.

## Sites

| Site | What | Where |
|---|---|---|
| Bush Point | Hydrophone | Admiralty Inlet, off Whidbey Island |
| North San Juan Channel | Hydrophone | North San Juan Channel |
| Orcasound Lab | Hydrophone | Haro Strait, west side of San Juan Island |
| Sunrise, Mount Rainier | Webcam | Mount Rainier National Park |
| West side, Mount Rainier | Webcam | Mount Rainier National Park |

Coordinates are published at the same approximate precision the feed operators publish, never
finer, and reports cover past windows rather than live positions. See METHODS.md.

## Credits and licensing

The feeds belong to other people and are used with attribution under their own terms. NOTICE
lists every source; it is generated from the feed registry rather than maintained by hand.

Hydrophone audio is courtesy of [Orcasound](https://www.orcasound.net), licensed
CC BY-NC-SA 4.0. Webcam imagery is courtesy of the National Park Service, Mount Rainier
National Park.

Licensing here is not one answer. Original material is CC BY 4.0, site code is MIT, and each
report carries the licence its sources impose, recorded in that report's `report.json`.
Reports built from Orcasound audio are CC BY-NC-SA 4.0. See LICENSE.

## Affiliation

A personal research project by Brian Rain. **Not a Microsoft product, and not affiliated with
or endorsed by the Microsoft AI for Good Lab.** Not affiliated with or endorsed by Orcasound,
the National Park Service, or any other feed operator; their material is used under the
public terms linked in NOTICE.
