# PopBar Extensions

PopClip-compatible extensions for the [Enconvo](https://enconvo.com) PopBar.

Enconvo installs PopClip extensions (`.popclipext` folders and `#popclip`
snippets) as plugins, and their actions appear as buttons on the PopBar. This
repository is Enconvo's catalog of the extensions it has reviewed. Enconvo is
not affiliated with or endorsed by Pilotmoon Software; PopClip is their
product and trademark.

Browse the catalog at [app.enconvo.com/popbar-extensions](https://app.enconvo.com/popbar-extensions),
or in Enconvo under **Settings → Plugins → PopClip Extensions**.

## What's here

| Path | What it is |
|---|---|
| `catalog.json` | The list Enconvo and the web page read. Each entry pins an upstream repository at a commit, every file's SHA-256 and the folder's digest. |
| `icons/` | Each listed extension's icon, drawn from the extension's own icon. |
| `ports/` | Upstream extensions changed to work in Enconvo, each with its original licence notice. |
| `extensions/` | Extensions written for Enconvo, by Enconvo or by contributors. |

## How the catalog is trusted

Enconvo installs a catalog extension only when the files it downloads match
the reviewed version byte for byte: every file's SHA-256 and the folder's
digest have to match `catalog.json`. Sources are pinned to a commit, so a
change upstream can't reach anyone until it is reviewed again. When the files
don't match, Enconvo refuses the install and says the version changed upstream.

Updates of a catalog extension arrive only when its reviewed version changes,
and Enconvo asks again before an update that adds scripts, network access or
apps it controls.

Not listed for now: extensions that sign in to an account, extensions that
build their buttons from each selection, and extensions whose buttons only
show information.

## Submitting an extension

Open a pull request that adds your extension as `extensions/<Name>.popclipext`
(see the [PopClip extension format](https://www.popclip.app/dev/)). Say what it
does and why it needs any scripts, network access or apps. After review, a
maintainer adds a `catalog.json` entry pinned to the reviewed commit.

To change an upstream extension so it works in Enconvo, add the changed copy
under `ports/` with the upstream licence notice kept.

## Licences

Listed extensions are downloaded from their upstream repositories at the
pinned commits and keep their own licences. The first batch comes from
[pilotmoon/PopClip-Extensions](https://github.com/pilotmoon/PopClip-Extensions)
(`source/`, MIT, Copyright (c) 2012 Nicholas Moore and contributors); see
`icons/LICENSE` for the icons drawn from it. Files under `ports/` keep their
original notices. Everything else in this repository is MIT licensed (see
`LICENSE`). Product names and logos belong to their owners.
