# Hokkaido 2026

Autumn trip plan · Oct 15–25, 2026 · Sapporo → Higashikawa → Sōunkyō → Jozankei → Lake Tōya → Noboribetsu → Sapporo

**Live:** https://dew-s.github.io/Hokkaido_2026/

## Files

| File | What it is |
|---|---|
| `index.html` | The plan. Content only — no styles inline |
| `assets/style.css` | All styling. Shared by every page |
| `README.md` | This file |

## Why the split

`index.html` holds only content, so a change to one day card shows up as a
three-line diff instead of being buried in 160 lines of CSS. Styling changes
live in `assets/style.css` and never touch the content file.

## Structure of index.html

```
<header>        title, date chips, sun summary
<div class=wrap>
  <div class=mapcard>   inline SVG route map + zoom inset
<nav>           section jump links
<div class=wrap>
  seclabel  #group      section heading
  div.day   ×11         one card per day  ← most edits happen here
  seclabel  #ref        reference tables
  ul.todo               still-to-confirm list
<footer>
```

### Anatomy of a day card

```html
<div class="day">
  <div class="n">      day number, date, weekday, party size
  <div class="body">
    <div class="stay">     where you sleep
    <div class="txt">      the day in one or two sentences
    <div class="times">    timeline, times in <b>
    <div class="plc">      places, as a <dl> of name + description
    <div class="lite">     light window  (add .dusk for sunset, .none for no light)
    <div class="warn">     caution  (add .ok for a good-news note)
    <span class="badge">   category tag
```

## Editing

Quickest route: open the repo and press `.` — that launches github.dev,
a full VS Code editor in the browser. Edit, then commit from the left panel.

Or locally:

```bash
git clone https://github.com/dew-s/Hokkaido_2026.git
cd Hokkaido_2026
# edit
git add -A && git commit -m "D5: shift Senbo departure to 04:00"
git push
```

GitHub Pages redeploys in about a minute.

## Class reference

| Class | Renders as |
|---|---|
| `.lite` | Sunrise block — warm amber |
| `.lite.dusk` | Sunset block — plum |
| `.lite.none` | No light available — grey |
| `.lk` | The small outlined label: Sunrise / Sunset / No light |
| `.warn` | Red caution box |
| `.warn.ok` | Green good-news box |
| `.badge.b-peak` | Red tag — big day |
| `.badge.b-good` | Amber tag |
| `.badge.b-turn` | Green tag — transition |
| `.badge.b-flex` | Purple tag — flexible |
| `.jpn` | Japanese place name, muted |
| `.z` | De-emphasised aside |
| `.star` | ★ rating |

## Conventions

- Place names stay in Roman + Japanese script so they match signage and Google Maps
- Sun times come from the National Astronomical Observatory of Japan, adjusted per location
- No sun emoji in light blocks — use the `.lk` text label
- One file per language; all share `assets/style.css`
