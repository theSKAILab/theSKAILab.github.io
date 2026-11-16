# Maintaining the SKAI Lab website

This guide accompanies the [README](README.md). It records the SKAI Lab changes to the [Academic Website Template](https://github.com/sbryngelson/academic-website-template) and explains how to make routine updates in the GitHub browser interface.

The new site launched on **November 12, 2026**. These instructions were checked against the `source` branch on November 16, 2026.

- **Live website:** <https://theskailab.github.io/>
- **Repository:** <https://github.com/theSKAILab/theSKAILab.github.io>
- **Editing and deployment branch:** `source`
- **Deployment workflow:** **Build and Deploy**, defined in `.github/workflows/deploy.yml`

Commits to `source` now trigger publication of the live website. GitHub handles the build; routine browser maintenance requires no local Jekyll server, Ruby installation, or GitHub Desktop.

## What was customized

| Area | SKAI Lab changes |
| --- | --- |
| Home and navigation | Lab introduction, logo variants for light and dark mode, teal accent, favicon, and navigation for Home, Team, Research, Publications, and News. Homepage research links point to the corresponding project cards. The sidebar shows a short director profile and two recent Highlights. |
| Team and contact | Director information is separated from the lab identity in `_data/director.yml`. The Team page and homepage sidebar use this data. Current member cards use initials when the photo field is blank. The former-member table contains SKAI Lab records. The footer links to Team for contact information, names the maintainers, credits the template, and uses an automatic ending copyright year. |
| Research | Profiles for SAWGraph, Digital Forest Knowledge Graph, CelloGraph, and Macleod. Each project keeps its related ontologies, software, publications, and funding information together. |
| Publications | Lab publications replace the example bibliography. The page groups records by publication type, hides empty categories, and provides a filter by title, author, or year. The citation settings emphasize Torsten Hahmann’s name. |
| News | Lab news and features replace the examples. The same data feed the homepage Highlights and the full News page. |

## Make an update in GitHub

For a routine update that is ready to publish:

1. Open the repository and select the **`source`** branch using the branch selector above the file list.
2. Open the file listed below and click the **pencil icon** to edit it.
3. Review the changes, click **Commit changes…**, and enter a short message such as `Add new lab member` or `Add FOIS publication`. Commit directly to `source` if repository permissions allow it and the change is ready to go live.
4. Open **Actions → Build and Deploy** and check the newest run for your commit. Once both jobs succeed, check the changed page on the live website.

There is no separate **Push origin** step when editing in GitHub's browser interface: the commit is already on GitHub. GitHub’s editor preview shows the file or its changes; it does not render the full Jekyll website.

For changes needing review, or several files that should publish together, create an update branch from `source` first. Make all edits and uploads on that branch, then open a pull request with **base: `source`**. Review **Files changed** and merge when ready. The merge publishes the update. A pull request does not by itself provide a rendered website preview.

To upload a photo or PDF, open the destination folder and choose **Add file → Upload files**. If publishing directly to `source`, upload the asset before adding the content that refers to it. An unused uploaded image is harmless; a reference to a missing image displays a broken photo.

See GitHub’s instructions for [editing files](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files) and [uploading files](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository). Routine browser edits do not require GitHub Desktop or a local Ruby installation.

## Find the right file

| Update | File or folder |
| --- | --- |
| Publication records and resource links | `assets/ref.bib` |
| News items and homepage Highlights | `_data/news.yml` |
| Current members | `_data/team_members.yml` |
| Former lab members | `_data/alumni.yml` |
| Director titles, education, photo, and affiliation | `_data/director.yml` |
| Director's short research biography and Team page structure | `_pages/team.md` |
| Homepage introduction, project summaries, and ontology links | `_pages/home.md` |
| Project profiles, funding information, and resource chips | `_pages/research.md` |
| Team photos | `images/team/` |
| Research images | `images/research/` |
| Locally hosted publication PDFs | `papers/` |
| Menu, lab identity, external profile links, site description, and accent | `_config.yml` |
| Homepage sidebar and number of Highlights | `_includes/sidebar.html` |
| Footer wording and links | `_includes/footer.html` |

Edit the source files, not `_site/`: `_site/` is generated during the build.

## Add a publication

Open **`assets/ref.bib`**. Copy an existing record of the same type, give the new record a unique key (for example, `lastname2026shorttitle`), and replace the fields with the published citation. Authors are separated with `and`, as in `author = {Last, First and Other, First}`. Check author order, year, venue, and DOI against the publisher’s record.

| Publication | BibTeX entry type | Website section |
| --- | --- | --- |
| Journal article | `@article` | Journal Articles |
| Conference or workshop paper | `@inproceedings` | Conference and Workshop Papers |
| Chapter in an edited book | `@incollection` | Book Chapters |

- Use `doi` for the identifier alone and `url` for a full web address. Add `code` for a relevant repository or `abstract` if an abstract should appear on the site.
- For a PDF stored in the repository, upload it to **`papers/`** and set `file` to the exact filename. For an externally hosted PDF, use `url`.
- Add book chapters using `@incollection` when their publication details are available. The Book Chapters heading appears automatically once there is a matching record.
- Preserve braces around acronyms, for example `{PFAS}` and `{OnNER}`, so citation formatting retains the capitalization. Each entry needs balanced braces and commas between fields.
- The file order does not control the displayed order: the configuration sorts records by year and month, descending. Add a month when known if the ordering within a year matters.

The page reads and sorts the bibliography automatically. Edit **`_pages/publications.md`** only to change the page structure or categories. The current page shows only the three entry types above; other types require a page change. Adding a preprint record alone will not display it. Keep the existing single-line filter input inside its `markdown="0"` wrapper.

Citation title formatting is in **`citesty.csl`**; the author name to bold is set under `scholar:` in **`_config.yml`**. After publishing a record, check its category, author order, links, BIB button, and visibility when filtering by title, author, or year.

## Add a news item

Open **`_data/news.yml`** and copy a nearby entry. Put the newest item at the top: the list is displayed in file order, not automatically sorted by date. Dates use the format `16 November 2026`. The `headline` field holds the entire item, including its bold lead, description, and link. Follow this structure, replacing the example text:

```yaml
- date: "16 November 2026"
  headline: >-
    <strong>Title of the update.</strong>
    A short description of the lab activity or announcement.
    <a href="https://example.org/story">Read the source organization’s announcement</a>.
```

Indent every content line beneath `headline` by four spaces. Use HTML such as `<strong>` and `<a>` inside the field, matching the existing entries. Label an outside link with its destination, such as “Read the UMaine News article.”

The first two entries appear under **Highlights** on the homepage. The full list appears on **News**, so one edit updates both places. Check the link in both locations after publication.

## Add or update a team member

1. Open **`_data/team_members.yml`** and copy a current member’s entry. Update `name`, `role`, and `info`. Use **`profile`**, not `profile_url`, for a personal or university profile; it displays a Website chip. Use `orcid` for the full ORCID URL, if available.
2. Upload the photo to **`images/team/`**. In the member record, use a path such as `photo: "team/FirstLast.jpg"`. Match the filename and capitalization exactly. Leave `photo` blank if no photo is available; the card uses initials.
3. If someone leaves the lab, remove their current entry and add a row to **`_data/alumni.yml`** in the same update. Use `name`, `role`, `duration`, `degree`, and `info`. The `info` field supplies the Current Position column. Leave unavailable fields as `""`. Former member rows do not need photos.

The current Team page places all entries in `team_members.yml` under **Research Assistants**. Adding a postdoctoral researcher or a different member category also requires adjusting the heading or grouping in **`_pages/team.md`**; the `role` field does not create a new section automatically.

Update the director’s shared profile information in **`_data/director.yml`**, and his research biography in **`_pages/team.md`**. His Google Scholar and ResearchGate links come from **`_config.yml`**. Check both the Team card and homepage sidebar after a director profile change.

For `.yml` files, preserve the existing indentation and use spaces rather than tabs. Keep the dash before each new member or news entry. Empty photo fields produce initials; a nonempty path to a missing file does not.

## Update other content

| To change | Edit |
| --- | --- |
| Homepage introduction or featured project links | `_pages/home.md` |
| Project descriptions, images, funding, or resource links | `_pages/research.md`; put new project images in `images/research/` |
| Site description, menu, or accent color | `_config.yml` |
| Footer contact, resource links, or template credit | `_includes/footer.html` |

When editing a project card, keep its existing `id` unless you also update the homepage links that point to it. Keep photos and other assets on the same update branch as the content that references them.

Current project IDs are `sawgraph`, `digital-forest`, `cellograph`, and `macleod`. The homepage summaries and project cards are separate text, so update both when their descriptions need to change together.

The footer has a three-column information area followed by centered maintenance, template-credit, and copyright lines. Its ending copyright year updates when the site rebuilds. Footer styling is in `_sass/components/_footer.scss`; link underline exceptions are in `_sass/base/_reset.scss`.

## Verify publication of an update

GitHub Pages is configured to use **GitHub Actions**. **`.github/workflows/deploy.yml`** builds and deploys on pushes to `source`, including browser commits and merged pull requests. There is no need to reselect GitHub Actions for each update. Leave the Pages publishing source and deployment permissions in their working configuration. The workflow supplies `url` and `baseurl` from Pages settings.

After committing or merging an update, open **Actions → Build and Deploy**, select the newest run for that commit, and check that both **build** and **deploy** succeeded. Then visit the live site and check the changed page, links, and images. Test layout changes on a narrow screen and in light and dark modes.

- **Old error still visible:** check the date and commit. Failed runs retain their errors even after a later run succeeds.
- **Newest build fails:** open the failed job and read the first error. Check YAML indentation, BibTeX braces, and recently edited HTML before making a correction commit.
- **Deploy fails with a branch-protection error:** ask a repository administrator to check that the `github-pages` environment permits `source`. This was addressed for the launch; an earlier rejected run is not evidence of a new problem.
- **Page appears unchanged after a successful deployment:** refresh the browser, then use a hard refresh if needed. Confirm you edited `source` and are viewing the live URL.
- **Broken image:** check the full relative path, file extension, and exact capitalization.

To restore a previous version of a file in the browser, open the file's **History**, locate the last working version, and copy its contents. Return to the current `source` branch and restore those contents in a new edit and commit. Verify the resulting deployment.

See [GitHub’s guide to custom Pages workflows](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages) and [viewing workflow runs](https://docs.github.com/en/actions/how-tos/monitor-workflows/view-workflow-run-history).

## Keep this guide with the repository

Store this file as **`MAINTAINING.md`** beside `README.md`. Link it from the README:

```markdown
[Maintaining the SKAI Lab website](MAINTAINING.md)
```

To keep the guide out of the built website, add this item to the existing `exclude:` list in `_config.yml` (do not create a second `exclude:` list):

```yaml
  - MAINTAINING.md
```

Update this guide when data fields, file locations, or the publishing process change. Keep the template README and this lab-specific guide together so a future template update does not erase the lab's maintenance instructions.
