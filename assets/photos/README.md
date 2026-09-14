# Photos

Drop trip photos here, then tell Claude the filenames to wire them in.

## Naming

`<place>-<subject>.jpg`, all lowercase, hyphens not spaces:

```
sounkyo-village.jpg
sounkyo-kurodake.jpg
sounkyo-gorge.jpg
biei-shinei-sunset.jpg
blue-pond-dawn.jpg
```

## Before committing

Resize to **1600 px on the long edge** and save at ~80% JPEG quality.
Aim for **under 400 KB each**. Phone originals are 4-8 MB — pushing a
few dozen of those bloats the repo permanently, because git keeps every
version forever.

Quick check for oversized files:

```bash
find assets/photos -name '*.jpg' -size +500k
```

## Credit

Photos from the local guide are credited in the page. Keep the credit
line when adding more from the same source.
