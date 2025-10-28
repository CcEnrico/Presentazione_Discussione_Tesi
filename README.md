# Presentazione Beamer — Compilazione con latexmk

Questo repository contiene la presentazione Beamer della discussione di tesi.
Di seguito trovi i comandi per compilare con `latexmk` e generare il file PDF con nome desiderato: `presentazione_enricoCottiCottini.pdf`.

## Requisiti
- TeX Live recente (pdflatex)
- latexmk
- biber (solo se usi bibliografia)
- makeglossaries (solo se usi glossari)
- cairosvg (necessario per convertire SVG e drawio in PDF secondo le regole in `.latexmkrc`)
- sed (già presente su molte distribuzioni Linux)

Esempio installazione su Ubuntu/Debian:
```zsh
sudo apt update
sudo apt install texlive-full latexmk biber python3-cairosvg
```

Nota: nel file `.latexmkrc` sono già configurati:
- `--shell-escape` e `--synctex=1`
- directory ausiliarie in `build/` (`$aux_dir = 'build'`)
- percorso dei temi `beamertheme/` tramite variabile d'ambiente `TEXINPUTS`
- regole per convertire `.svg` e `.drawio.svg` in PDF

## Compilazione (PDF con nome personalizzato)
Per generare direttamente `presentazione_enricoCottiCottini.pdf` dalla sorgente `main.tex` usa l’opzione `-jobname` di latexmk:
```zsh
latexmk -pdf -jobname=presentazione_enricoCottiCottini main.tex
```
- Il PDF viene creato nella cartella del progetto con il nome specificato.
- I file ausiliari finiscono in `build/` (grazie alla configurazione in `.latexmkrc`).

Se preferisci il nome predefinito (ad es. `main.pdf`):
```zsh
latexmk -pdf main.tex
```

## Anteprima continua (ricompilazione automatica)
```zsh
latexmk -pdf -pvc -jobname=presentazione_enricoCottiCottini main.tex
```
- `-pvc` (preview continuously) rimane in esecuzione e ricompila ad ogni salvataggio.

## Pulizia
- Pulizia “leggera” (mantiene il PDF):
```zsh
latexmk -c
```
- Pulizia “completa” (rimuove anche il PDF):
```zsh
latexmk -C
```

## Note su temi e immagini
- I file del tema sono in `beamertheme/` e la ricerca è già configurata in `.latexmkrc` via `TEXINPUTS`.
- Se un tema richiede immagini come `unipd_logo.png`, assicurati che LaTeX possa trovarle:
  - opzione A: metti l’immagine nella root del progetto, oppure
  - opzione B: dichiara un percorso immagini nel preambolo del tuo `main.tex`:
    ```tex
    \usepackage{graphicx}
    \graphicspath{{images/}}
    ```
  - opzione C: usa percorsi relativi direttamente nei comandi `\includegraphics`, come già fatto in `main.tex` (es. `images/Contesto_Applicativo/valvola_sfera.png`).


## Struttura tipica output
- PDF finale: `./presentazione_enricoCottiCottini.pdf` (se usi `-jobname`)
- File ausiliari: `./build/` (log, aux, nav, snm, ecc.)

---
Se vuoi integrare i comandi in un Makefile o in uno script, puoi usare il comando con `-jobname` mostrato sopra per ottenere sempre il nome PDF desiderato.
