# HSK Tutor plugin attribution

Production release 3.1.1. All learner handoff links contain only `utm_source=claude`. Example: `https://hsk-tutor.com/mock-exam/HSK3?utm_source=claude`. No medium or campaign is added.

The existing website `lib/amplitude.ts` retains source/medium/campaign in sessionStorage and adds them to subsequent event properties. Existing mock-exam code emits `assessment_started`, `assessment_completed`, `assessment_submit_failed`, `assessment_section_started` and `mock_exam_results_viewed`, including `hsk_level`. No website analytics code was changed for this release.

In Amplitude filter `utm_source = claude`. Funnel: `page_viewed` on `/mock-exam/...` → `assessment_started` → `assessment_completed` → `mock_exam_results_viewed`. Segment by `hsk_level`; exclude `internal_traffic = true`. Site visits/starts/completions are measurable when events arrive and tracking is permitted; they are not counts of chat messages or exact outbound clicks. Source-only attribution does not distinguish releases or separate Claude plugins. Existing sessionStorage can retain old medium/campaign values from earlier links: do not use those fields to filter this release.

CPC = attributable campaign spend / measured clicks. There is no advertising spend or exact outbound-click logger supplied by this skills-only plugin, so do not display a made-up CPC. A proxy cost-per-landing-visit can be calculated separately if spend is known, but must not be labelled CPC. Plugin installs and skill usage require the publisher's Claude directory metrics, not UTM links.

Blocked analytics, stripped parameters, shared links, bot filtering and browser privacy controls can reduce attribution. No personal IDs, answers, recordings or chat transcripts are placed in the URLs. Tracking disclosure must match the website privacy policy. The production Amplitude ingestion/dashboard was not verified in this local package preparation.
