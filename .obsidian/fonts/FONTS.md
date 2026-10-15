# Fonts

Font files are not checked in. Obsidian picks fonts by family name from those installed on the system. It never loads anything from this folder.

`appearance.json` asks for:

- Interface: `Inter`, falling back to `Inter Variable`
- Text: `Inter Variable`, falling back to `Inter`
- Monospace: `Dank Mono`

`snippets/font.css` turns on Inter's OpenType features (`cv11`, `ss01`, `ss02`, `ss07`, `zero`).

If a font is missing, Obsidian falls back to its default. Nothing breaks.

## Inter

Inter 4.1 by Rasmus Andersson, under the SIL Open Font License 1.1. The release has three font files:

- `Inter.ttc` provides the `Inter` family (static weights).
- `InterVariable.ttf` and `InterVariable-Italic.ttf` provide the `Inter Variable` family.

Install them in one of these ways:

- NixOS: `fonts.packages = [ pkgs.inter ];` (nixpkgs ships the same three files)
- Home Manager: `home.packages = [ pkgs.inter ];` with `fonts.fontconfig.enable = true;`
- macOS: `brew install --cask font-inter`
- By hand: download `Inter-4.1.zip` from <https://github.com/rsms/inter/releases/tag/v4.1> (or <https://rsms.me/inter/>), then install the three files above with your OS font installer

Restart Obsidian after installing.

## Dank Mono

Dank Mono is a commercial font by Phil Plückthun: <https://dank.sh>. If you don't have it, choose another monospace font in Settings → Appearance → Font.
