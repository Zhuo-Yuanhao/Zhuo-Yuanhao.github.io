# Yuanhao Zhuo — Academic Website

Source repository for the personal academic website of **Yuanhao “Martin” Zhuo**, PhD Candidate in Computer Science at the University of Wollongong.

The site is built with the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template and hosted with GitHub Pages.

## Current setup

The first-stage setup includes the homepage biography, academic profile links, contact information, and a publications landing page. CV, detailed publication entries, research/project pages, teaching, and other sections will be populated incrementally.
## Publishing a dormant section

Unused pages and template sample collections are retained in the repository but
excluded from the site build via `exclude` in `_config.yml`. This keeps them out
of both `/sitemap/` and `/sitemap.xml`, and prevents their URLs from being published.
The current public content is the homepage and publications landing page.

To enable a section, replace its template content, remove the matching page and
collection paths from `exclude`, and add its link to `_data/navigation.yml` if
needed. The `_publications` collection currently contains only template examples;
the real publication list is maintained in `_pages/publications.html`.
Restart Jekyll after editing `_config.yml`.

For a published page that should simply be omitted from both sitemaps, add
`sitemap: false` to its YAML front matter. Its URL will still be accessible.
