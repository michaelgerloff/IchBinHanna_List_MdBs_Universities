# IchBinHanna – List of Bundestag Members with Universities in Their Constituency

## Purpose
This project aggregates the names, email addresses, and constituency information of members of the German Bundestag (MdBs) whose constituencies include at least one university or college (Hochschule). The goal is to help researchers contact their local representatives in the context of the ongoing debate around the reform of the Wissenschaftszeitvertragsgesetz (WissZeitVG).

## Getting Started
Clone the repository and navigate into it:

```bash
git clone https://github.com/michaelgerloff/IchBinHanna_List_MdBs_Universities.git
cd IchBinHanna_List_MdBs_Universities
```

The `Output/` folder contains the latest generated Excel files which can be used directly without running the notebook:

- **MdBs_mit_Hochschulen_im_Wahlkreis.xlsx**
- **Hochschulen_mit_MdBs_im_Wahlkreis.xlsx**

To regenerate the files from scratch, follow the Prerequisites and Running the Notebook sections below.

## Output
The project produces two Excel files:

- **MdBs_mit_Hochschulen_im_Wahlkreis.xlsx** — one row per MdB, with a list of all universities in their constituency
- **Hochschulen_mit_MdBs_im_Wahlkreis.xlsx** — one row per university/MdB combination, useful for looking up which MdBs to contact for a given university

## Prerequisites
### Kürschners Volkshandbuch
The email addresses of MdBs are extracted from the Kürschners Volkshandbuch, which is freely available as a PDF:

1. Download the PDF from: https://www.btg-bestellservice.de/pdf/10037700.pdf
2. Convert it to a plain text file
3. Place it at `Input/Kürschners_Volkshandbuch.txt`

### Conda Environment
Create and activate the project environment:

```bash
conda env create -f environment.yml
conda activate MdBs_Unis
```

## Data Sources
- **Abgeordnetenwatch API** — constituency and fraction membership data for all MdBs: https://www.abgeordnetenwatch.de/api/v2
- **HRK Hochschulkompass** — list of all German universities and colleges: https://hs-kompass.de/kompass/xml/download/hs_liste.txt
- **Bundeswahlleiter** — constituency shapefiles: https://www.bundeswahlleiter.de

## Running the Notebook
Open `Hanna.ipynb` in VSCode or JupyterLab and run all cells in order. Note that the first run will geocode all university addresses via Nominatim, which takes approximately 6-7 minutes. Subsequent runs use a cached file and skip geocoding unless the university list has changed.

## Acknowledgements
Thanks to [@gudlot](https://github.com/gudlot) for paired programming contributions to the original version of this project.