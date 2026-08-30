---
name: email-write
description: Draft, rewrite, translate, and review professional or marketing emails in Thai, English, or bilingual form. Use for workplace correspondence, requests, follow-ups, announcements, newsletters, outreach, promotions, email subject lines, preheaders, plain-text email, responsive HTML email, or when turning notes and attached documents into polished email copy.
---

# Email Write

Create email copy that is clear, concise, polite, and productive. Default to
Thai unless the user requests another language. Preserve names, facts, dates,
links, and commitments from source material.

## Workflow

1. Inspect the user's prompt and attachments before asking questions.
2. Identify purpose, recipient and relationship, desired outcome, tone,
   language, key facts, deadline, and signature details.
3. Ask only for missing facts that materially affect accuracy. Never invent
   recipients, commitments, prices, dates, evidence, or contact details.
4. Select the appropriate mode:
   - Use **Professional** for workplace email, requests, replies, follow-ups,
     apologies, meeting notes, announcements, and transactional messages.
   - Use **Marketing** for outreach, newsletters, launches, promotions,
     re-engagement, case studies, and conversion-focused messages.
5. Draft the shortest complete email. Use short paragraphs and bullets when
   they improve scanning.
6. Verify grammar, spelling, tone, factual fidelity, request clarity, and
   attachment references before delivery.

## Professional Mode

Use this structure unless the source material calls for another:

1. A specific subject line
2. A greeting appropriate to the relationship
3. A first sentence stating context or purpose
4. Essential details in a logical order
5. One explicit request or next step, including deadline when provided
6. A polite closing and signature

Keep the message natural rather than stiff. Avoid vague subjects, unnecessary
background, repeated requests, inflated language, and unexplained acronyms.
When rewriting, retain the author's intent while improving clarity and tone.

## Marketing Mode

Read [references/copy-frameworks.md](references/copy-frameworks.md) before
drafting. Choose a framework based on purpose; do not force a marketing
framework onto ordinary workplace email.

Unless the user requests a shorter deliverable, return:

- Three subject variants: curiosity, benefit, and urgency
- A recommended subject with a brief rationale
- A complementary preheader
- The email body with one primary CTA
- Plain text
- Responsive HTML only when requested

Use personalization supported by user data. Do not fabricate social proof,
scarcity, urgency, or results. Avoid spam-like capitalization, punctuation,
and promises.

## Output

For ordinary requests, return:

```text
Subject: ...

...
```

For review or rewrite tasks, provide the polished version first. Add concise
notes only when they help the user decide between alternatives.

For bilingual requests, keep both versions structurally aligned and flag
phrases where literal translation would sound unnatural.

## Quality Gate

Before delivering, confirm:

- The subject is specific and matches the body.
- The opening makes the purpose clear.
- The recipient can identify the requested action and timing.
- Tone matches the relationship and requested language.
- Every factual claim comes from supplied context.
- Greeting, closing, and signature are present when appropriate.
- Attachments mentioned in the email actually exist in the supplied context.
- Marketing output follows the chosen framework without misleading claims.
