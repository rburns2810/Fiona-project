# Fiona's Pocket Reader 📖

A small e-ink EPUB reader, built and personalised as a Christmas 2026 gift.

> 🤫 This repo is private. Keep it that way until after Christmas.

## The plan in one paragraph

We use an **M5Stack M5PaperS3**. It's an all-in-one e-ink board with a 4.7" touch screen, a built-in battery, a microSD slot and its own case, so **no soldering is needed**. We flash it with **CrossPoint Reader**, an open-source (MIT) EPUB reader firmware that has a community port for the PaperS3. Then we add Fiona's personal touches: her name on the boot and sleep screens, a dedication page, and a starter library of books on the SD card.

## Hardware

See [`docs/parts-list.md`](docs/parts-list.md). **Order this week**: shipping can take 1–2 weeks.

| | |
|---|---|
| Board | M5Stack M5PaperS3 (ESP32-S3, 8 MB PSRAM, 16 MB flash) |
| Screen | 4.7" e-ink, 960×540, 16 grey levels, capacitive touch |
| Power | 1800 mAh Li-Po built in, USB-C charging |
| Storage | microSD (books live here) |

## Firmware

Base: [`struthio/crosspoint-reader-m5-paper`](https://github.com/struthio/crosspoint-reader-m5-paper), a PaperS3 port of [CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader). Both are MIT-licensed.

- EPUB 2/3, chapters, bookmarks, footnotes, hyphenation
- Touch controls: tap the left or right third of the screen to turn pages, tap the centre for the menu, swipe up or down to turn pages
- Built with PlatformIO

Notes:
- The port's last commit was April 2026 (v1.2.0). Upstream CrossPoint is very active but doesn't target the PaperS3, so we may backport fixes as needed.
- The port's README shows `esptool --chip esp32c3`. That's wrong for this board; use **`--chip esp32s3`**.

## Personal touches (planned)

- [ ] Custom boot / sleep screen ("Fiona's Library" + a picture)
- [ ] A dedication "book" (EPUB) that opens first: a note from me
- [ ] Starter library on the SD card (her favourites + some public-domain classics)
- [ ] Gift wrap: microSD pre-loaded, device charged, short "how to use" card

## Timeline

| By | Step |
|---|---|
| Nov 30 | Order parts |
| Dec 1–10 | Fork firmware into `firmware/`, add custom screens, build in CI |
| Parts arrive | Flash, test reading, battery life, sleep/wake |
| Dec 15 | Load books + dedication, final test |
| Dec 20 | Charge, wrap 🎁 |

## Repo layout

```
docs/        parts list, build & flashing notes, how-to-use card
firmware/    (coming) customised CrossPoint PaperS3 firmware
books/       (coming, git-ignored) EPUBs for the SD card
```
