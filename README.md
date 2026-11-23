# etc

Aaron Hightower's shell environment. Dotfiles for iSH on iPhone — TCSH, aliases, tab completion, and an installer that only writes files that aren't already there.

This is the setup behind everything else: two phones, iSH as the shell, Simple Server for preview, GitHub as version control. Work comes back as a zip, gets previewed on the phone, and goes into a repo with the same filename rebuilt in place.

## What's in here

| File | What it does |
| ---- | ------------ |
| `_tcshrc` | Shell startup. Sources `_alias` and `_complete`, sets the prompt. |
| `_alias` | All the aliases: directory jumps, git shortcuts, commit helper, yt-dlp. |
| `_bashrc` | One line: `t` drops you into tcsh. |
| `t` | A one-letter command for tcsh. Copy it to `/bin` and chmod +x, then `t` starts tcsh from anywhere. |
| `motd` | The login message. Says to type `t` to get into tcsh. |
| `_complete` | Tab completion: `unzip`/`zip` complete `*.zip`, `ga` completes files. |
| `_vimrc` | Search highlighting, yellow on black. |
| `install_dotfiles` | Copies `_bashrc`, `_vimrc`, `_tcshrc` into place as `.profile`, `.vimrc`, `.tcshrc`, and `t` into `/bin` — only if they don't already exist. Never overwrites. |
| `auth` | Credentials. Not documented here. |

## The aliases that matter

Directory jumps, two or three letters so there's nothing to type on a phone keyboard:

`cell` CELLTOWER, `dis` district, `sto` stories, `ser` sermon, `kar` karaoke, `piz` pizza, `let` letters, `pa` / `pal` prior-art, `aa` aahigh, `etc` this repo.

Git, made for a phone keyboard:

- `st` status, `ga` add, `com <message>` commit with a message and push, `pull`, `push`, `up` pull with rebase from origin main
- `cleaf` removes untracked files (`git clean -fd`), `hard` restores tracked files (`git reset --hard HEAD`)
- `clean` dry-run clean, `https` fixes the remote URL to https with the right case

Media and upkeep:

- `ytdlp` is yt-dlp, because the dash is annoying on a phone keyboard
- `sa` reloads the aliases, `va` edits them

## Workflow

Everything is built on the phone. Request in plain words, get a zip back, preview it on iSH with Simple Server, push the folder to its repo. The repos this environment serves: cellTower, district, stories, sermons, tracks, karaoke, and the rest of the High Tower District.

Current work running through this setup: CELLTOWER skill tournaments, the pizza platform, Suno track pages, and karaoke production (DJI Mic Mini, ffmpeg in iSH, mix page at karaoke.ahightower.com/rec).

## Skill library

The skill library — thirteen skills covering writing, stories, sermons, Suno tracks, karaoke production, and prior art — is packaged as `aaron-skills.zip` in the aahigh repo. This environment is what those skills run in.

## Assistant

Buddy (Muse) is the assistant now. The old README described a collaboration with Claude; that's history. Current work runs through Buddy.

## Install

Run `./install_dotfiles` from this repo. It only installs files you don't already have. It installs once — it will not replace a file that is already there. If one is outdated, delete it first, then run the installer again.
