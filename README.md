# Chen Qianyu / Xiaochen Codex Pet

`chen-qianyu` is a high-fidelity chibi anime Codex pet. Her full name is Chen Qianyu (`陈千语`), and Xiaochen (`小陈`) is her nickname.

The pet uses the standard Codex pet atlas layout: 8 columns by 9 rows, with 192x208 cells and the states `idle`, `running-right`, `running-left`, `waving`, `jumping`, `failed`, `waiting`, `running`, and `review`.

## Preview

![Contact sheet](qa/contact-sheet.png)

Selected animation previews are in [`previews/`](previews/).

## Install Locally

Copy the package folder into your Codex pets directory:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\pets\chen-qianyu"
Copy-Item -Path ".\pet\pet.json", ".\pet\spritesheet.webp" -Destination "$env:USERPROFILE\.codex\pets\chen-qianyu" -Force
```

Then select `custom:chen-qianyu` in Codex settings if your Codex build exposes custom pet selection by id.

## Petdex Submit

Petdex accepts either a pet folder or a zip whose root contains:

- `pet.json`
- `spritesheet.webp`

This repository includes a ready package at:

```text
dist/chen-qianyu-petdex.zip
```

Submit with:

```bash
npx petdex login
npx petdex submit ./pet
```

or:

```bash
npx petdex submit ./dist/chen-qianyu-petdex.zip
```

## QA

The final package is based on `edge-repair-v2`.

- Visual QA: pass
- Atlas validation: pass
- Spritesheet: `1536x1872`, WebP, RGBA
- Transparent RGB residue: `0`
- Installed/final SHA256: `75AE6E046064E12A6A38645CC4B2032942F6F4DA3248D6E15367145DDA170968`

Detailed validation artifacts are in [`qa/`](qa/).

## Notes

The local Codex install can keep the shorter id `xiaochen`; the public package uses `chen-qianyu` so the character's full name is clear.

Choose a license before publishing publicly if you want other people to remix, redistribute, or use the artwork outside personal Codex pet installs.
