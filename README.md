# HSK Tutor — chat preparation and website exams

This plugin teaches Chinese in chat using short Learn, Practise and Review sessions. It draws its teaching workflow from the HSK Tutor daily-study plan, without claiming access to the website's private course content or saved learner progress.

One entry: say "HSK Tutor" and choose vocabulary, grammar, daily practice, review or a mock exam. A direct request skips the menu. Vocabulary defaults to 10 level-appropriate words. Daily teaching remains Learn → Practise → Review.

Mock exams take place at https://hsk-tutor.com/mock-exam, not inside Claude. Known levels open the matching page, for example `/mock-exam/HSK3` or `/mock-exam/HSK5`. Links do not automatically start or submit an attempt. This plugin does not require MCP, localhost, a browser extension or an embedded HTML card. Ordinary chat lessons are AI-authored practice, not official HSK exam questions or scores.

Install `HSK-Tutor-Claude-Production.zip` through Customize > Plugins > Add > Upload plugin. Replace the previous HSK Mock Test version, and disable the separate Local Browser test plugin to avoid conflicting instructions. Display name is HSK Tutor; technical identity `hsk-mock-exam` remains stable so this can update the existing plugin. There is one discoverable skill, `hsk-tutor`; its supporting workflows are references, not extra commands. No connector setup is needed. Previously installed independent connectors are not automatically removed.

Ask "Give me 15 minutes of HSK 2 practice", "Explain this Chinese sentence", or "I want an HSK mock exam". The plugin has no separate database or progress-sync service. In-chat work is subject to Claude's own data handling; visiting the website is subject to its privacy policy. No production server change is included in this release.

Outbound website links include only `utm_source=claude`; no learner content or personal identifiers are appended. See `METRICS.md` for the website funnel and measurement limitations. Official HSK3.0 announcements are cited in the skill's dated reference, checked 2026-10-03. This package's structural validation is not a guarantee that a model will always follow the skill; no paid model-based behavioral eval was run.
