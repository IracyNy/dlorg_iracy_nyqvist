# Dlorg - Downloads Organizer

Dlorg är ett bash-script som automatiskt organiserar filer i `~/Downloads`.

## Funktioner
- Övervakar Downloads i realtid med `inotifywait`
- Flyttar filer baserat på filändelse
- Skapar mappar automatiskt om de saknas
- loggar till `~/.local/share/dlorg/dlorg.log`
- Kan köras som användartjänst med systemd

## Mappstruktur

| Mapp | Filändelser |
|---|---|
| docs | .docx, .doc, .odt |
| images | .jpg, .png, .gif, .webp |
| pdfs | .pdf |
| text | .txt, .md |
| videos | .mp4, .mkv, .avi, .mov |
| audio | .mp3, .wav, .flac |
| archives | .zip, .tar, .gz, .rar |
| code | .sh, .py, .js, .c, .java |
| other | Allt annat |

## Installation

```bash
git clone git@github.com:IracyNy/dlorg_iracy_nyqvist.git
cd dlorg_iracy_nyqvist
chmod +x dlorg
sudo dnf install inotify-tools
./dlorg
```

## Portabilitet
Använder `$HOME` istället för hårdkodade sökvägar. Systemd-tjänsten använder `%h` och körs som användartjänst utan root.

## Systemd (bonus)
Se `docs/systemd.md`.

## LLM-användning
LLM har använts som bollplank för att förstå `inotifywait` och `case`-satsen. Jag har skrivit och testat all kod själv. 

