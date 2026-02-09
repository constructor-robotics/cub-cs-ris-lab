# Projects

This folder contains all research project pages.

## Naming Convention

All project files should follow this naming convention:
```
<project-slug>.md
```

**Examples:**
- `sonar-cv.md`
- `acoustic-modem-energy-management.md`
- `legged-locomotion.md`

Use lowercase with hyphens (kebab-case) for project slugs.

## Creating a New Project

1. Copy the `TEMPLATE.md` file
2. Rename it following the naming convention above
3. **Remove** the `published: False` line from the frontmatter
4. Fill in the frontmatter:
   - `title`: Project Title (e.g., "Sonar Computer Vision")
   - `project`: project slug matching the filename (e.g., `sonar-cv`)
   - `primary_researcher`: Full Name
   - `status`: one of: `exploring` | `implementing` | `experiments` | `writing` | `wrapping-up` | `maintenance` | `concluded`
   - `nav_order`: adjust if needed for sidebar ordering
5. Fill in the content sections:
   - Update the heading and one-line description
   - Write the Overview section
   - Fill in Current Status details
   - List project Goals
   - Describe the Technical Approach
   - Add the Repository link

## Frontmatter Reference

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | Display title for the project |
| `layout` | Yes | Always `default` |
| `parent` | Yes | Always `Projects` |
| `nav_order` | Yes | Order in sidebar navigation |
| `project` | Yes | Project slug (must match filename) |
| `primary_researcher` | Yes | Lead researcher's full name |
| `status` | Yes | Current project status |

## Status Values

- `exploring` - Initial research and feasibility study
- `implementing` - Active development
- `experiments` - Running experiments and collecting data
- `writing` - Writing papers or documentation
- `wrapping-up` - Finalizing results
- `maintenance` - Ongoing maintenance
- `concluded` - Project completed

## Related WIP Entries

The template includes a Liquid loop that automatically lists all WIP entries matching the project slug. Ensure the `project` field in your WIP entries matches the `project` field in the project page
