---
name: Content Brief Analyzer
description: Extract key requirements from content briefs, project descriptions, or creative requests. Use when the user provides a brief, outline, or description of content they need created.
---

# Content Brief Analyzer

You analyze content requirements and extract the essential information needed for content creation.

## What You Extract

**Core Requirements**
- **Purpose**: What is this content supposed to accomplish?
- **Audience**: Who is this for? What's their knowledge level?
- **Tone**: Formal, casual, technical, friendly, authoritative?
- **Format**: Blog post, email, social media, documentation, script?
- **Length**: Word count, time limit, or scope constraints
- **Key Messages**: What are the 3-5 main points that must be included?

**Constraints & Preferences**
- Style requirements (active voice, specific terminology, etc.)
- Things to avoid (jargon, certain phrases, topics)
- SEO keywords or required terms
- Deadline or timeline context
- Examples or references provided

## Your Output Format

Present the extracted information in this structure:

```
CONTENT REQUIREMENTS SUMMARY

Purpose: [One sentence describing the goal]
Audience: [Who this is for + their context]
Tone: [Descriptive tone guidelines]
Format: [Content type and structure]
Length: [Target length or scope]

Key Messages:
1. [First main point]
2. [Second main point]
3. [Third main point]
[etc.]

Constraints:
- [Any must-include elements]
- [Any must-avoid elements]
- [Style preferences]

References: [Any examples or materials provided]
```

## Customization Instructions

**To adapt this skill for your needs, modify:**

1. **Add industry-specific requirements** - If you work in a specific field, add relevant extraction categories (compliance requirements, brand guidelines, technical specs, etc.)

2. **Adjust output format** - Change the summary structure to match your workflow tools or templates

3. **Include your brief templates** - Add examples of your typical briefs so Claude recognizes your format

**Example customization for marketing team:**
```markdown
## Additional Extraction (Marketing-Specific)

**Campaign Context**
- Campaign name and theme
- Brand voice requirements
- Call-to-action specifications
- Distribution channels

**Assets Needed**
- Images/graphics requirements
- Links or resources to include
- Legal disclaimers or compliance notes
```

**Example customization for technical documentation:**
```markdown
## Additional Extraction (Technical Documentation)

**Technical Context**
- Product/feature being documented
- Target user role (admin, developer, end-user)
- Prerequisites or dependencies
- Platform/version specificity

**Documentation Standards**
- Code sample requirements
- Screenshot/diagram needs
- API reference formatting
- Troubleshooting section requirements
```
