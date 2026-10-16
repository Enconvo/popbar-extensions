# PopBar Extensions

PopClip-compatible extensions for the [Enconvo](https://enconvo.com) PopBar.

Enconvo installs PopClip extensions (`.popclipext` folders and `#popclip`
snippets) as plugins, and their actions appear as buttons on the PopBar. This
repository is Enconvo's catalog of the extensions it has reviewed. Enconvo is
not affiliated with or endorsed by Pilotmoon Software; PopClip is their
product and trademark.

Browse the catalog at [app.enconvo.com/popbar-extensions](https://app.enconvo.com/popbar-extensions),
or in Enconvo under **Settings → Plugins → PopBar Extensions**.

## What's here

| Path | What it is |
|---|---|
| `catalog.json` | The list Enconvo and the web page read. Each entry pins an upstream repository or gist at a commit, every file's SHA-256 and the folder's digest. |
| `sources.json` | The repositories and gists the catalog is built from, each pinned to a commit with its author and licence. |
| `icons/` | Listed extensions' icons, drawn from their own icons where the source's licence allows copying them (see `icons/LICENSE`). |
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
build their buttons from each selection while also asking for network or script
access, and the pilotmoon extensions that PopClip's own directory has dropped
or unlisted (Bubble Translate, ChatGPT App, Deliveries, LaTeX to MathML, nvALT,
Short Menu, The Hit List and Translatium). Copies already installed from an
earlier catalog keep working.

## How the catalog is built

`scripts/build_catalog.ts` in Enconvo's `popclip` module reads `sources.json`,
fetches each source at its pinned commit, and runs the same checks Enconvo runs
at install. Each source names its author and licence, the category of its
extensions, and whether its licence lets the catalog copy its icon images. A
gist holding a `#popclip` snippet is staged the way Enconvo installs a snippet,
and its entry pins the gist's files and the staged folder's digest.

## Submitting an extension

Open a pull request that adds your extension as `extensions/<Name>.popclipext`
(see the [PopClip extension format](https://www.popclip.app/dev/)). Say what it
does and why it needs any scripts, network access or apps. After review, a
maintainer adds a `catalog.json` entry pinned to the reviewed commit.

To list an extension from your own repository or gist, add it to
`sources.json` with the commit to review, your name and its licence.

To change an upstream extension so it works in Enconvo, add the changed copy
under `ports/` with the upstream licence notice kept.

## Licences

Listed extensions are downloaded from their own repositories and gists at the
pinned commits and keep their own licences; each entry names its author and
licence. Most come from
[pilotmoon/PopClip-Extensions](https://github.com/pilotmoon/PopClip-Extensions)
(`source/`, MIT, Copyright (c) 2012 Nicholas Moore and contributors), and the
rest from the sources the [PopClip Extensions Directory](https://www.popclip.app/extensions/)
links to. Icons are copied only from sources whose licence allows it, and
`icons/LICENSE` carries each such source's notice; the others are drawn by
Enconvo from the installed files. Files under `ports/` keep their
original notices. Everything else in this repository is MIT licensed (see
`LICENSE`). Product names and logos belong to their owners.
