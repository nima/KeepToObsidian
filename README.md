# KeepToObsidian
Migrate from Google Keep to Obsidian

## Demo
Here's what to expect:
```bash
Verifying OBSIDIAN_P[/Users/nima/Library/Mobile Documents/iCloud~md~obsidian/Documents/Cristobalite]...PASS
Verifying EXPORT_P[/Users/nima/Library/Mobile Documents/iCloud~md~obsidian/Documents/Cristobalite/export/Keep]...PASS
Verifying IMPORT_P[/Users/nima/Library/Mobile Documents/iCloud~md~obsidian/Documents/Cristobalite/import/Keep]...PASS
Verifying IMAGES_P[/Users/nima/Library/Mobile Documents/iCloud~md~obsidian/Documents/Cristobalite/images]...PASS
Migrating from Google Keep to Obsidian...
 - Copying images..............................................................................DONE
 - Cepheid Variable Stars...DONE [Cepheid Variable Stars.json]
 - Prometheus ...DONE [Prometheus_.json]
 - Zhou (Chou) Dynasty π¨π³ 1046/1122β256 BCE...DONE [Zhou (Chou) Dynasty π¨π³ 1046_1122β256 BCE.json]
 - π Words...DONE [π Words.json]
 - US Garbage (4.5lb/day)...DONE [US Garbage (4.5lb_day).json]
 - ...DONE [2022-01-01T22_03_04.700-08_00.json]
 - Rock Folds...DONE [Rock Folds.json]
 - ...DONE [2021-12-17T20_05_37.202-08_00.json]
 - ι₯Ίε­ (Jiao Zi)...DONE [ι₯Ίε­ (Jiao Zi).json]
 - Earth's Core...DONE [Earth_s Core.json]
 - The Middle Ages ...DONE [The Middle Ages_.json]
 - Scandinavia...DONE [Scandinavia.json]
 - Crust: Rift Zones...DONE [Crust_ Rift Zones.json]
 - Chrisβs Notes...DONE [Chrisβs Notes.json]
 - π Germany π©πͺ ...DONE [π Germany π©πͺ_.json]
 - ...DONE [2022-01-29T21_55_19.925-08_00.json]
 - β³ 1700β1799 CE...DONE [β³ 1700β1799 CE.json]
 - π©Έ Berbers...DONE [π©Έ Berbers.json]
 - π Palestine π΅πΈ ...DONE [π Palestine π΅πΈ_.json]
 - βοΈ Clouds βοΈ π§ βοΈ...DONE [βοΈ Clouds βοΈ π§ βοΈ.json]
 - Water Table...DONE [Water Table.json]
 - Chinese π¨π³ Languages...DONE [Chinese π¨π³ Languages.json]
 - ...DONE [2022-04-29T18_49_26.581-07_00.json]
 - ...DONE [2021-12-17T20_05_44.802-08_00.json]
 - π The 12 Biogeographical Realms...DONE [π The 12 Biogeographical Realms.json]
 - π­ On Power...DONE [π­ On Power.json]
 - The Table of Nuclides...DONE [The Table of Nuclides.json]
 - Astronomical Distances...DONE [Astronomical Distances.json]
 - πΉ Options...DONE [πΉ Options.json]
 ...
 ```

## Instructions
Export some variables for the script in this repo; in my case (which is now the default in the script):
```bash
export OBSIDIAN_P="${HOME}/Library/Mobile Documents/iCloud~md~obsidian"
export VAULT_N="Cristobalite"
export IMAGES_D="images"
```

When you next run the script, it will do some validation, and if all goes well commence with the migration of your Google Keep data from the export area to the import.

Thence, to Google and download yout Keep repository; you have the option to do this as either a `.zip`, or a `.tgz`; the latter is more efficient.  They will send you an email once it is ready for download.

After receiving the email, download and untar/unzip that the `Keep` directory is moved and replaces `${EXPORT_P}`.

Now you can execute this script (from any `pwd`).

### Migration Quality
The migration is aware of the following:
- the `title`,
- the `labels` (to `tags` in Obsidian),
- the `images` (both the image and the reference to it from within the migrated note),
- the `created` and `modified` timestamps (in to Obsidian's front matter section) but in UTC (not local time), and in seconds (not microseconds as in Keep).
- and of course, the `body`.

## Caveats
There are a few thing you would need to run this on your Mac; I've not tested it out on Linux; these can all be installed via `brew`
- `jq`
- `gawk`
- `gfind`
