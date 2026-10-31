# Personal Website

Markus's personal website, built with [Astro](https://astro.build) (v7). It's an early-stage static site: the layout and navigation are in place, and most page content is still a placeholder.

## Getting Started

Requires Node.js `>=22.22.0`.

```sh
npm install
npm run dev
```

The dev server runs at `http://localhost:4321`.

## Commands

| Command             | Action                                        |
| :------------------ | :-------------------------------------------- |
| `npm install`       | Install dependencies                          |
| `npm run dev`       | Start the dev server at `localhost:4321`      |
| `npm run build`     | Build the production site to `./dist/`        |
| `npm run preview`   | Preview the production build locally          |
| `npm run astro ...` | Run Astro CLI commands (e.g. `astro check`)   |

To run the dev server in the background, use `astro dev --background`, and manage it with `astro dev stop`, `astro dev status` and `astro dev logs`.

## Project Structure

```text
src/
├── content/            # Markdown you write: reading/, projects/, writing/
├── content.config.ts   # Frontmatter schemas for those collections
├── data/site.ts        # Name, bio, links, nav, experience, education
├── layouts/BaseLayout.astro
├── components/
├── pages/              # index, about, experience, contact, reading, projects, writing
└── styles/global.css   # Tailwind entry
```

Styling uses Tailwind CSS v4 (with the typography plugin).

## Updating Content

- **Bio, links, jobs, education:** edit `src/data/site.ts`. Search for `TODO` to find placeholders.
- **Log a book:** copy `src/content/reading/geopolitical-alpha.md` to a new file in the same folder (the filename becomes the URL) and edit the details at the top (`status`: `reading`, `finished` or `want-to-read`). To add a cover, save the image in `src/assets/covers/` and set `cover:` to its path. When you finish a book, set `status: finished` and add `finished` and `rating`.
- **Add a project:** add a `.md` file to `src/content/projects/`.
- **Write a post:** add a `.md` file to `src/content/writing/` (set `draft: true` to hide it).
- **Resume:** put a PDF at `public/resume.pdf`.

The home page's "Now" section is built automatically from books marked `reading` and projects marked `in-progress` or `exploring`.

## Documentation

- [Astro docs](https://docs.astro.build)
- [Routing](https://docs.astro.build/en/guides/routing/)
- [Styling](https://docs.astro.build/en/guides/styling/)
