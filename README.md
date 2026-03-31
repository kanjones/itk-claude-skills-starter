# Content Creation Workflow Skills

Three composable Claude Skills that work together to handle your content creation process efficiently.

## What This Is

A skill suite that demonstrates the **agent/subagent approach** to context window management. Instead of loading all your instructions at once, each skill handles a specific part of your workflow. Claude automatically pulls from the relevant skill(s) when needed.

**The Three Skills:**
1. **Content Brief Analyzer** - Extracts and structures requirements from your content requests
2. **Draft Generator** - Creates first drafts based on those requirements
3. **Quality Reviewer** - Reviews content against requirements and your quality standards

## Why This Matters

**Traditional approach:** You paste your brand guidelines + writing rules + review checklist into every conversation. Your context window fills up fast.

**Skills approach:** Each skill loads only when needed. Claude sees "they're asking about requirements" and loads the Brief Analyzer. Then sees "they want a draft" and loads the Draft Generator. Your context window stays efficient.

**Agent approach:** These three skills act like specialized subagents. Brief Analyzer knows how to extract requirements. Draft Generator knows how to write. Quality Reviewer knows how to review. They pass work between each other automatically.

## How They Work Together

**Example conversation flow:**

```
You: "I need a blog post about password security for small business owners"

Claude: [Loads Content Brief Analyzer]
"I've analyzed your requirements:
Purpose: Educate small business owners on password security
Audience: Non-technical business owners
Tone: Helpful and accessible, not fear-mongering
..."

You: "Yes, write that"

Claude: [Loads Draft Generator, references the brief]
[Produces 600-word draft matching requirements]

You: "Review this before I publish"

Claude: [Loads Quality Reviewer, references both brief and draft]
"HIGH PRIORITY: Add specific examples in the 'common mistakes' section
MEDIUM PRIORITY: Simplify the two-factor authentication explanation
Overall: Ready to publish with minor edits..."
```

Each skill only loads when it's needed for that specific task. You're not carrying all three instruction sets simultaneously.

## Installation

### Step 1: Download and Customize

1. Download all three skill folders from this package
2. Open each `SKILL.md` file
3. Read the "Customization Instructions" section in each
4. Add your specific requirements, voice samples, or standards

**Start simple:** You can use them as-is without customization. Add your specific rules as you go.

### Step 2: Create Skill Packages

For each skill:

1. Make sure the folder structure is correct:
   ```
   content-brief-analyzer/
   └── SKILL.md
   
   draft-generator/
   └── SKILL.md
   
   quality-reviewer/
   └── SKILL.md
   ```

2. Zip each folder individually:
   - Right-click the folder → "Compress" (Mac) or "Send to → Compressed folder" (Windows)
   - You should end up with three .zip files

### Step 3: Upload to Claude

1. Go to Claude.ai settings
2. Navigate to **Settings → Capabilities → Skills**
3. Click "Upload Skill"
4. Upload each .zip file one at a time
5. Enable code execution if prompted

**Important:** You need a Claude Pro, Max, Team, or Enterprise plan to use Skills.

## Recommended Setup

### Start with One Skill

Install just the **Quality Reviewer** first. It's immediately useful even without the others - just use it to review any content you've already written.

Test it:
```
"Review this email for clarity and tone:
[paste your email]"
```

### Add the Second Skill

Once you're comfortable, add the **Draft Generator**. Now you can:
```
"Write a 300-word email to my team about the new project timeline. 
Keep it encouraging but honest about the challenges."
```

### Add the Third Skill

Finally, add the **Content Brief Analyzer** for complex projects:
```
"I need to create a user guide for our new software feature. 
It's for beginner users who are switching from a competitor product. 
Should be friendly and include screenshots. About 2000 words."
```

The analyzer will structure those requirements, the generator will draft it, and the reviewer will check it.

## Customization Examples

### For Bloggers

**In Quality Reviewer, add:**
```markdown
## My SEO Requirements
- Primary keyword in first 100 words
- Meta description in opening paragraph (under 155 chars)
- 3+ H2 headings with keyword variations
- Internal links to 2+ related posts
- Images with descriptive alt text
```

### For Marketing Teams

**In Draft Generator, add:**
```markdown
## Brand Voice Rules
- Never use: "innovative," "cutting-edge," "revolutionary"
- Always emphasize: Real results, specific numbers, stories
- Tone: Confident but not arrogant, helpful but not patronizing
```

### For Technical Writers

**In Content Brief Analyzer, add:**
```markdown
## Additional Extraction (Technical Docs)
**Technical Context**
- Product/feature being documented
- Target user role (admin, developer, end-user)
- Prerequisites or dependencies

**Documentation Standards**
- Code sample requirements
- Screenshot/diagram needs
- API reference formatting
```

## Advanced Usage

### Multi-Skill Workflows

These skills compose automatically. You don't need to tell Claude "use both the Draft Generator and Quality Reviewer." Just ask naturally:

```
"Write me a product announcement email and then review it for clarity"
```

Claude will:
1. Use Draft Generator to create the email
2. Use Quality Reviewer to check it
3. Present both the draft and the review

### Skill as Reference

The skills stay available across conversations. Start a new chat and ask:

```
"What are my brand voice rules?"
```

Claude will reference your customized Draft Generator skill to tell you.

### Iterative Improvement

As you use the skills, you'll notice gaps. Add to them incrementally:

- Draft Generator keeps using words you don't like? Add them to your "Terms to Avoid" section
- Quality Reviewer missing things? Add them to your "Non-Negotiable Standards"
- Getting the same clarifying questions? Add defaults to Brief Analyzer

## Troubleshooting

**Skill isn't triggering when expected:**
- Check the description in the YAML frontmatter (top of SKILL.md)
- Make it more specific about when to use the skill
- Example: Change "helps with content" to "creates first drafts of blog posts, emails, and social media content"

**Claude loads wrong skill:**
- Descriptions might be too similar
- Make each description more distinct about its specific role

**Skill triggers too often:**
- Description might be too broad
- Add specific constraints about when NOT to use it

**Quality isn't consistent:**
- Add more examples in the customization section
- Include samples of your actual writing style
- Be more specific about requirements

## What to Do Next

1. **Install Quality Reviewer first** - Test it on content you've already written
2. **Customize one thing** - Pick the most annoying part of your current workflow and add rules for it
3. **Use it for a week** - See what works, what doesn't
4. **Add another skill** - Once you're comfortable, add Draft Generator
5. **Iterate** - Keep refining based on what you actually need

## File Structure Reference

Your final setup should look like this:

```
content-brief-analyzer.zip
├── SKILL.md (with your customizations)

draft-generator.zip
├── SKILL.md (with your voice samples and rules)

quality-reviewer.zip
├── SKILL.md (with your quality standards)
```

## Need Help?

**Common questions:**

*Do I need all three skills?*
No. Start with one, add more as needed.

*Can I modify the skills after uploading?*
Yes. Edit the SKILL.md file, re-zip, and re-upload.

*Do these work with other skills?*
Yes. Claude can pull from these plus any other skills you have installed.

*What if I don't want to customize them?*
Use them as-is. They work fine with generic settings. Customize later when you hit friction.

## Credits

Created as a demonstration of composable Claude Skills for context window efficiency. Based on the agent/subagent workflow pattern.

---

**Version:** 1.0  
**Last Updated:** March 2026  
**Compatibility:** Claude Pro, Max, Team, Enterprise plans
