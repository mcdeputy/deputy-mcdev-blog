# Deputy's McDev Blog

[DeputyMc.Dev](https://deputymc.dev)

Made using [AstroPaper](https://github.com/satnaing/astro-paper), a theme for [Astro](https://github.com/withastro/astro).

Domain registered with [Porkbun](https://porkbun.com/), hosted using Cloudflare [Workers](https://workers.cloudflare.com/) and [DNS](https://www.cloudflare.com/en-au/application-services/products/dns/).

## Usage/Reminders

[Markdown Reference](#-markdown-reference) - For blog posts & READMEs  
[Posts/Pages](#-posts--pages) - Storage, creation & editing  
[Assets](#️-assets) - Storage & creation  
[Customization/Variables](#-customization--variables) - Theme, fonts, site width, social links etc.  
[Added Features](#-added-features)
[OG AstroPaper Docs](#-astropaper-docs)

## 📜 Markdown Reference

| Item | Description |
| ----------- | ----------- |
| Heading | `## Heading` - Number of # dictates heading level |
| Page Separator/Divider/Wide Line | `---`|
| Italic Text | `*My italic text.*` - *My italic text* |
| Bold Text | `**My bold text.**` - **My bold text** |
| New Line In Paragraph | Two spaces at end of line, followed by more text on immediate next line.<br>`<br>` to force in table. |
| Link - Internal Heading | `[Link Text](#markdown-reference)` - [Link Text](#markdown-reference) |
| Link - External Site | `[My Google Link](https://www.google.com)` - [My Google Link](https://www.google.com) |
| Link - Internal public/assets (not auto-optimized) image | `![My internal public image](/assets/godot-64x64.webp)` ![My internal public image](/assets/godot-64x64.webp) |
| Link - Internal src/assets (auto-optimized) image | `![My internal blog image](@/assets/icons/IconArchive.svg)` ![My internal blog image](@/assets/icons/IconArchive.svg) |
| Escape/Ignore Special Characters | `Backslash \\ is used before character.` - Backslash \\ is used before character. |
| Escape/Ignore Special Characters in Inline Code | ``` `` `inline code` `` ``` - `` `inline code using varying amounts of tilde` `` |
| Table | \| Syntax      \| Description \|<br>\| ----------- \| ----------- \|<br>\| Item1 \| It's an item \|<br>\| Item2 \| Probably also an item \|
| Inline Code | `` `My inline code` `` - `My inline code` |
| Code Block (Bash for markdown) | ```` ```bash````<br>`Code block line 1`<br>`1Code block line 2`<br>```` ``` ```` |

## 📰 Posts & Pages

Further info in [Add Posts](#-astropaper-docs)

### Storage

Base website pages such as home, about are stored in src\pages

Posts are stored in `src\data\blog` as Markdown .md files.

### Creation/Editing

While editing, run `pnpm run dev` in terminal to preview while editing (ctrl+click link)

Create new .md in directory listed above.

Alternatively if editing an already existing post, in Frontmatter (top):  
Add `modDatetime: 2025-01-08T18:59:05Z` under `pubDatetime: 2025-01-03T20:40:08Z`.

## 🖼️📺 Assets

Public images stored in public\assets will not be auto optimized or anything by Astro.

Blog icons and images stored in src\assets\images.
Non-icon images compressed to WebP using [TinyPNG](https://tinypng.com/).

Videos uploaded to [YT @DeputyMcDev](https://www.youtube.com/@DeputyMcDev).
Remember that many videos are unlisted.

## 🟩✅ Customization & Variables

### Base Website Settings

Website title, posts per page and other basic settings defined in `src\config.ts`.

### Theme - Colors/Page Width

Website theme colors, maximum width defined in src\styles\global.css.

### Font

Steps using [Fontsource](https://fontsource.org/) as example.

1. Import with terminal command  
`pnpm add @fontsource/space-mono` or `pnpm add @fontsource-variable/inter`.
2. Define/import at top of src\layouts\Layout.astro  
Files will have been added to node_modules\@fontsource or @fontsource-variable  
`import "@fontsource/space-mono";` or `import "@fontsource-variable/inter";`.
3. Include in src\styles\global.css  

```bash
@theme inline {
  --font-mono: "Space Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  --font-sans: "Inter Variable", ui-sans-serif, system-ui, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  --color-background: var(--background);
  etc;
}
```

4. Change font in different places it's defined.  
Default everywhere - src\styles\global.css - @layer base{body}  
`@apply flex min-h-svh flex-col bg-background font-sans text-foreground selection:bg-accent/75 selection:text-background;`  
Headers, such as homepage - src\pages\index.astro  

```bash
<h1 class="my-4 inline-block text-4xl font-sans font-bold sm:my-8 sm:text-5xl">
  My title
</h1>
```

### Socials

Socials defined in src\constants.ts
Socials are automatically listed by components that request them, auto listing all defined ones.

## 🔥 Added Features

Comments added with [Giscus](https://astro-paper.pages.dev/posts/how-to-integrate-giscus-comments/).

## 📖 AstroPaper Docs

- Core - [markdown](https://github.com/satnaing/astro-paper/tree/main/src/data/blog) | [blog post](https://astro-paper.pages.dev/posts/)

- Configuration - [markdown](https://github.com/satnaing/astro-paper/tree/main/src/data/blog/how-to-configure-astropaper-theme.md) | [blog post](https://astro-paper.pages.dev/posts/how-to-configure-astropaper-theme/)
- Add Posts - [markdown](https://github.com/satnaing/astro-paper/tree/main/src/data/blog/adding-new-post.md) | [blog post](https://astro-paper.pages.dev/posts/adding-new-posts-in-astropaper-theme/)
- Customize Color Schemes - [markdown](https://github.com/satnaing/astro-paper/tree/main/src/data/blog/customizing-astropaper-theme-color-schemes.md) | [blog post](https://astro-paper.pages.dev/posts/customizing-astropaper-theme-color-schemes/)
- Predefined Color Schemes - [markdown](https://github.com/satnaing/astro-paper/tree/main/src/data/blog/predefined-color-schemes.md) | [blog post](https://astro-paper.pages.dev/posts/predefined-color-schemes/)