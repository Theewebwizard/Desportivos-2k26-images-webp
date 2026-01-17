Images folder structure and jsDelivr usage

This repository stores image assets in per-page folders so they can be referenced directly from jsDelivr CDN.

Folder layout (created):

- Landing
- Sports
- Aftermovie
- PastArtists
- GalleryCircular
- AboutUs
- Team
- Sponsors
- Rulebook
- Registration
- GalleryFront
- Assets (shared logos, icons, misc)

Naming & conventions

- Use lowercase, hyphens for filenames: `hero-01.jpg`, `team-member-01.webp`.
- Prefer webp/optimized formats where possible for smaller size.
- For retina images, add `@2x` suffix before extension: `hero-01@2x.webp`.
- Keep folder usage consistent: page-specific assets in their page folder, shared items in `Assets`.

Serving via jsDelivr

1. Commit and push your images to GitHub.
2. Use the jsDelivr gh CDN URL format:

   https://cdn.jsdelivr.net/gh/<github-username>/<repo>@<tag-or-commit>/images/<Folder>/<file>

Example (recommended: use a tag or commit hash for cache stability):

https://cdn.jsdelivr.net/gh/youruser/Desportivos-2k26-images@v1.0.0/images/Landing/hero-01.webp

If you prefer to point to the latest branch (less stable for caching), you can use the commit hash or a release tag instead of `v1.0.0`.

React usage examples

- In JSX:

```jsx
<img
  src="https://cdn.jsdelivr.net/gh/youruser/Desportivos-2k26-images@v1.0.0/images/Landing/hero-01.webp"
  alt="Hero"
  loading="lazy"
/>
```

- In CSS:

```css
.hero {
  background-image: url("https://cdn.jsdelivr.net/gh/youruser/Desportivos-2k26-images@v1.0.0/images/Landing/hero-01.webp");
}
```

Best practices

- Pin to a tag or commit for production to avoid unexpected changes and to leverage long-term CDN caching.
- Make a small release/tag after adding images and reference that tag from your app.
- Use `loading="lazy"` for non-critical images to improve LCP.
- Keep shared assets (icons, logos) in `Assets` to avoid duplication.

Quick git commands to publish assets and tag a release:

```bash
git add images/
git commit -m "Add image asset folders and images"
git push origin main
# create a tag for stable CDN URLs
git tag v1.0.0
git push origin v1.0.0
```

Want me to:

- Move existing images into these folders and update local imports in code (I can do this), or
- Just leave the structure and instructions and you’ll add images yourself?

If you choose moving images, tell me where the current images live (list or path) and I'll relocate and update imports in the repo.
