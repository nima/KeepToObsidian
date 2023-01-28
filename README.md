# KeepToObsidian
Migrate from Google Keep to Obsidian

## Instructions
Export some variables for the script in this repo; in my case (which is now the default in the script):
```bash
export OBSIDIAN_P="${HOME}/Library/Mobile Documents/iCloud~md~obsidian"
export VAULT_N="Cristobalite"
export IMAGES_D="images"
```

When you next run the script, it will do some validation on these path, and from them construct the following; this is just informational; you need not do anything futher here:
```bash
OBSIDIAN_P+="/Documents/${VAULT_N}"
EXPORT_P="${OBSIDIAN_P}/export/Keep" # Exporting from json out of here
IMPORT_P="${OBSIDIAN_P}/import/Keep" # Importing to markdown in here
IMAGES_P="${OBSIDIAN_P}/${IMAGES_D}" # Importing images here
```

Thence, to Google and download yout Keep repository; you have the option to do this as either a `.zip`, or a `.tgz`; the latter is more efficient.  They will send you an email once it is ready for download.

After receiving the email, download and untar/unzip that the `Keep` directory is moved and replaces `${EXPORT_P}`.

Now you can execute this script (from any `pwd`).

### Migration Quality
The migration is aware of the following:
- the `title`,
- the `labels` (to `tags` in Obsidian),
- the `images` (both the image and the reference to it from within the migrated note),
- the `created` and `modified` timestamps,
- and of course, the `body`.
