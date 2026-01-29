# WIP (Work-in-Progress) Entries

This folder contains all work-in-progress log entries.

## Naming Convention

All WIP entries should follow this naming convention:
```
YYYY-MM-DD__<project_slug>__<presenter>.md
```

**Examples:**
- `2024-03-15__tactile-grasping__john-doe.md`
- `2024-04-02__legged-locomotion__jane-smith.md`
- `2024-05-10__slam-mapping__alex-johnson.md`

## Creating a New WIP Entry

1. Copy the `templates/TEMPLATE.md` file
2. Rename it following the naming convention above
3. Fill in the frontmatter:
   - `title`: "WIP: <project_slug> - <presenter> (<YYYY-MM-DD>)"
   - `date`: YYYY-MM-DD
   - `project`: project slug (e.g., tactile-grasping)
   - `presenter`: Full Name
   - `tags`: relevant tags for the entry
   - `status`: one of: exploring | implementing | experiments | writing | wrapping-up | maintenance
4. Fill in the content sections with your update

## Project Slugs

Common project slugs (keep it consistent):
- `tactile-grasping`
- `legged-locomotion`
- `slam-mapping`

For new projects, use lowercase with hyphens (kebab-case).
