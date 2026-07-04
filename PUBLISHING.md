# Publishing Options

## Best First Path

1. Push this repository to GitHub.
2. Create a GitHub Release and attach `dist/chen-qianyu-petdex.zip`.
3. Submit the same package to Petdex.

## GitHub

Use GitHub as the canonical source page:

- `pet/pet.json`
- `pet/spritesheet.webp`
- `previews/*.gif`
- `qa/contact-sheet.png`
- `qa/edge-check-sheet.png`
- `qa/validation.json`
- `dist/chen-qianyu-petdex.zip`

GitHub Releases are useful for download links because release assets can hold binary ZIP/WebP files.

## Petdex

Petdex is the most relevant discovery channel for Codex-compatible pets.

Submit either:

```bash
npx petdex submit ./pet
```

or:

```bash
npx petdex submit ./dist/chen-qianyu-petdex.zip
```

## Other Channels

- OpenAI Community: good for showing the pet, install steps, and GitHub link to other Codex users.
- itch.io: good if you want a polished asset-pack page or optional tips/pay-what-you-want downloads.
- OpenGameArt: only if you are comfortable releasing under an accepted open/free art license.
- Pixiv / ArtStation / X / Bluesky / Bilibili: good for artwork showcase and process posts, with GitHub/Petdex links.
- Discord communities: useful for feedback and early installs, especially Petdex/Codex/AI-coding communities.

## License Decision

Before broad public distribution, decide whether this is:

- all rights reserved, portfolio/share-only;
- free personal use;
- CC BY 4.0;
- CC BY-NC 4.0;
- CC0/public domain;
- another custom license.

OpenGameArt and similar free-asset sites require compatible open/free licenses, so do not submit there until the license is intentional.
