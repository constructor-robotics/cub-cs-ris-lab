# People Directory

This folder contains individual markdown files for each lab member.

## Naming Convention

All people files should follow this naming convention:
```
firstname__lastname.md
```

**Examples:**
- `juan__perez-chavez.md`
- `bernard__fromm.md`

Use lowercase with double underscore between first and last name. Use hyphens for compound last names.

## Adding a New Person

1. Copy the `TEMPLATE.md` file
2. Rename it following the naming convention above
3. **Remove** the `published: False` line from the frontmatter
4. Fill in the frontmatter fields (see Frontmatter Reference below)
5. Fill in the content sections (see Content Sections below)
6. **Upload a profile picture** to `/assets/people/` with the naming format `firstname-lastname.png` (or `.jpg`), then update the image path in your file

## Profile Picture

Each person should have a profile picture displayed next to their name and research focus.

- Upload your picture to: `/assets/people/firstname-lastname.png` (or `.jpg`)
- Update the `<img src=...>` tag in your markdown file to point to your picture
- If no picture is available, the template uses `/assets/people/default.jpg` as a placeholder

## Frontmatter Reference

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | "Firstname Lastname" |
| `layout` | Yes | Always `default` |
| `parent` | Yes | Always `People` |
| `nav_order` | Yes | Order in sidebar navigation |
| `first_name` | Yes | First name |
| `last_name` | Yes | Last name |
| `group` | Yes | Lab role category (see Group Values) |
| `honorific_title` | No | Title prefix (e.g., `Dr.`, `Prof.`, `PhD`) |
| `last_degree` | No | Highest degree (e.g., `PhD`, `MSc`, `BSc`, `Bachelors`) |
| `public_url` | No | Personal website URL |
| `status` | Yes | `active` or `inactive` |
| `offboard` | No | `yes` or `no` |
| `research_focus` | No | Brief research description |

## Group Values

- `faculty` - Faculty and staff members
- `phd` - PhD students
- `masters` - Master's students
- `undergrad` - Undergraduate students
- `external` - External collaborators

## Status Values

- `active` - Current lab member (displayed in main sections)
- `inactive` - Former lab member (displayed in Alumni section)

## Content Sections

Each person page has three main sections:

### About
Brief introduction with the following suggested bullets:
- **Background:** Previous education, institution, or relevant experience
- **Research Interests:** Specific topics or problems you're interested in
- **Current Work:** What you're currently working on in the lab
- **Skills:** Programming languages, tools, or methodologies you use
- **Hobbies:** Interests outside of work

### Current Projects
Automatically lists projects where the person is the `primary_researcher`. The filter matches projects where `primary_researcher` contains both the first and last name.

### Related WIP Entries
Automatically lists WIP entries where the person is the `presenter`. The filter matches entries where `presenter` contains both the first and last name.

## Offboarding

When a member leaves the lab:
1. Set `status: inactive`
2. Optionally set `offboard: yes`

They will automatically be moved to the Alumni section on the People page.
