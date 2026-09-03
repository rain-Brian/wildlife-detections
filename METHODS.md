# Methods

How the reports in this repository are produced, and what they can and cannot support.

## The pipeline

Public feeds are captured continuously, archived, run through detection models, and rendered
as reports. Capture and inference are separate: nothing that detects runs inside the process
that records, so a model change cannot cost recording time.

| Feed | Model | What it decides |
|---|---|---|
| Orcasound hydrophones | OrcaHello | Whether a killer whale call is present in a window |
| Orcasound hydrophones | Ecotype classifier | Which population a call is more consistent with |
| Mount Rainier webcams | MegaDetector | Whether an animal, person or vehicle is in a frame |
| Underwater video | YOLO-Fish with a YOLO-World second pass | Whether a fish or a larger animal is in a frame |

## What a detection is

A model output. Nothing on these pages is a confirmed identification unless it says a person
reviewed it, and reviewed cards are marked and kept visually distinct from model output.

OrcaHello is a **call-presence detector**. It answers whether a killer whale call is in the
window. It does not identify pod, individual, or call type, and no report here should be read
as saying it does.

## False-positive floors

A detection is only shown if its confidence clears the false-positive floor **measured at
that specific site for that specific label**.

Floors are measured, not assumed: windows where the label should not appear are run through
the model, and the rate at which it fires anyway becomes the floor. A label with no measured
floor gets no card at all, however confident the model was. That rule exists because this
project once displayed a humpback label at 0.97 confidence when humpback had no measured
floor whatsoever.

Floors are **per site**. Pooling them across hydrophones lets a site with heavy traffic clear
a threshold on its own volume and then license claims at a quiet site that never earned one.
That happened here and was corrected.

## Review queues

Some pages here are not results. They are **queues**: model output published before anyone
has judged it, so the queue itself can be checked and so changes to the pipeline can be seen
from outside.

A queue page is marked `model candidate` and says so at the top. Nothing on one is an
identification. The floors above do not license it, and cannot: the underwater video and
fixed-camera models have no measured false-positive floor at all. That is precisely why these
are published as queues rather than as detections. Where a floor exists, a detection clears it
or is not shown. Where none has been measured, the honest choices are to publish nothing or to
publish the output plainly labelled as unreviewed, and publishing it is what lets a reader
disagree with a specific card. Those disagreements are the material a floor is eventually
built from.

Queue pages carry a verdict layer. Judging a card records it in your own browser and the
export button hands back a file; nothing is transmitted. A queue is never counted alongside
reviewed evidence: every finding on the front page carries its status, and the reviewed count
is separate from the candidate count.

## Presence is plotted per day

Counts alone cannot distinguish 446 detections spread over eighteen days from 30 in a single
afternoon. The first is a claim about every day the site was listening; the second is one
encounter. Reports plot presence per day for that reason.

## Coverage

Every report states the hours of usable signal it covers. Feeds fail, nodes go offline, and
hardware degrades in ways that leave a recording running while the signal is dead. A gap in
detections may be a gap in animals or a gap in listening, and only the coverage figure
separates them.

"Usable" is stricter than "recording". One hydrophone in this network kept producing
perfectly well-formed audio files for five days after its acoustic signal died, and every
liveness check called it healthy.

## Negative controls

A second model agreeing with the first is not corroboration until it has been tested on
material where it should disagree.

A general-purpose whale classifier was evaluated as a second opinion here and rejected. It
ranked killer whale first on 77.5% of windows the primary detector had marked negative,
against 79.3% on windows dense with genuine calls. That near-identical rate is a baseline
prior of an out-of-distribution model, not agreement, and without the negative control it
would have read as confirmation. Any second-opinion model used in a report here has been
through the same test.

## Locations and a deliberate choice

Site coordinates are published at the approximate precision the feed operators themselves
publish, and never at a finer resolution.

Reports cover **past windows only**. There is no live feed on this site and no real-time
position for any animal. Publishing a detection at a location is a different act from the
underlying feed being public, and for a species subject to disturbance the distinction
matters. Approximate positions plus historical windows keep the reports scientifically
useful without making them a tracking tool.

## Limits

- Model outputs, not sightings, except where a card says a person confirmed it.
- Call-presence detection does not identify pod, individual, or call type.
- Ecotype classification is a comparison of consistency, not a determination.
- Coverage is uneven. Feeds fail and are not always restored quickly.
- Absence of detections is never evidence of absence of animals.
- A queue page is unreviewed model output, not a result, and its counts are not findings.

## Sources

Feeds, their operators and their terms are listed in NOTICE, generated from the feed
registry. Each report additionally records its own sources, models, model versions, run
identifiers and effective licence in its `report.json`.
