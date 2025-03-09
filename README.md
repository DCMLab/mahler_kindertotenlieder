![Version](https://img.shields.io/github/v/release/DCMLab/mahler_kindertotenlieder?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/mahler_kindertotenlieder)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/mahler_kindertotenlieder](https://github.com/DCMLab/mahler_kindertotenlieder) and the corresponding
* documentation page [https://dcmlab.github.io/mahler_kindertotenlieder](https://dcmlab.github.io/mahler_kindertotenlieder)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/mahler_kindertotenlieder/introduction).

# Gustav Mahler – Kindertotenlieder (A corpus of annotated scores)

This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards).
It represents the canonical voice-and-piano edition of Mahler's 1904 orchestral song cycle after Rückert. This work,
along with the contemporaneous Rückert-Lieder and Symphony no. 5, represent an introversion of the composer's style
alongside an increase in harmonic experimentation. This trend is reflected in our annotations by the presence of complex
non-standard contrapuntal patterns within single harmonies as well as in prolongating, non-cadential chord successions.
In expanding the possibilities of chromatic elaboration and free organization of functional harmonies, these phenomena
illustrate a connection between 19th- and 20th-century styles represented elsewhere in the Distant Listening Corpus.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/mahler_kindertotenlieder/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [mahler_kindertotenlieder.zip](https://github.com/DCMLab/mahler_kindertotenlieder/releases/latest/download/mahler_kindertotenlieder.zip)
  * [mahler_kindertotenlieder.datapackage.json](https://github.com/DCMLab/mahler_kindertotenlieder/releases/latest/download/mahler_kindertotenlieder.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/mahler_kindertotenlieder.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first song, *Nun will die Sonn’ so hell aufgeh’n!* has the following files:

* `MS3/kindertotenlieder_01_nun_will_die_sonn.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/kindertotenlieder_01_nun_will_die_sonn.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/kindertotenlieder_01_nun_will_die_sonn.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/kindertotenlieder_01_nun_will_die_sonn.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/kindertotenlieder_01_nun_will_die_sonn.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/kindertotenlieder_01_nun_will_die_sonn.harmonies.tsv")
notes = ms3.load_tsv("notes/kindertotenlieder_01_nun_will_die_sonn.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/mahler_kindertotenlieder/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/mahler_kindertotenlieder/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Gustav Mahler – Kindertotenlieder (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Scores

These piano scores were downloaded from the wonderful [OpenScore Lieder](https://musescore.com/user/27638568/sets/5051725) project. They correspond to the ca.1911 Universal Edition printing of the vocal score. Staff spacing, paginations, and margins were modified to improve the readability of the annotations. 

## Overview
|                file_name                |measures|labels|standard|annotators |reviewers|
|-----------------------------------------|-------:|-----:|--------|-----------|---------|
|kindertotenlieder_01_nun_will_die_sonn   |      84|   179|2.3.0   |Amelia Brey|DK       |
|kindertotenlieder_02_nun_seh_ich_wohl    |      74|    96|2.3.0   |Amelia Brey|AN       |
|kindertotenlieder_03_wenn_dein_mutterlein|      70|   118|2.3.0   |Amelia Brey|AN       |
|kindertotenlieder_04_oft_denk_ich        |      71|    53|2.3.0   |Amelia Brey|AN       |
|kindertotenlieder_05_in_diesem_wetter    |     139|   149|2.3.0   |Amelia Brey|ST       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
