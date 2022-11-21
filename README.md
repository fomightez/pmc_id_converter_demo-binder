# ID converter between PMID, PMCID and DOI
> https://www.ncbi.nlm.nih.gov/pmc/tools/id-converter-api/

## Installation
```bash
python3 -m pip install pmc-id-converter
```

## Usage
### Command Line
```bash
id_converter --help

# PMID
id_converter 30003000
# PMCID
id_converter PMC6039336
# DOI
id_converter 10.1007/s13205-018-1330-z
# Multiple IDs
id_converter 30003000 30003001 30003002
# Output to a file
id_converter 30003000 30003001 30003002 -o out.json
```