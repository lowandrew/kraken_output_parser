# kraken_output_parser

Given a standard Kraken report, creates a nice CSV file showing number of reads assigned to each member of whatever
taxonomy level you choose (so, for example, the number of reads assigned to each genus). Can also do subsets of the tree
of life with the `-t` option, so you could look only at taxonomy within your favourite phylum/class/order/whatever else.


### Installation

You'll need `python 3.5` and the `ete3` package - recommended to install with pip in a virtualenv:

`pip install ete3`

To use, clone this repository and use the `kraken_parser.py` script. If you feel like it, put the script on your $PATH
so it can be accessible from anywhere.


### Usage
```
usage: kraken_parser.py [-h] -i INPUT_FILE [INPUT_FILE ...]
                        [-l {Unclassified,Kingdom,Domain,Phylum,Class,Order,Family,Genus,Species,Other}]
                        [-t TAXONOMY] -o OUTPUT_FILE [-f]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT_FILE [INPUT_FILE ...], --input_file INPUT_FILE [INPUT_FILE ...]
                        Path to one or more kraken output file(s), generated
                        by kraken-report. Separate each file with a space.
  -l {Unclassified,Kingdom,Domain,Phylum,Class,Order,Family,Genus,Species,Other}, --level {Unclassified,Kingdom,Domain,Phylum,Class,Order,Family,Genus,Species,Other}
                        Taxonomy level you want a report for. Defaults to
                        Family level.
  -t TAXONOMY, --taxonomy TAXONOMY
                        Subset of data to look at (i.e. only look at families
                        within Firmicutes). Defaults to examining all
                        bacteria.
  -o OUTPUT_FILE, --output_file OUTPUT_FILE
                        Path to output file. Will be written in CSV format.
  -f, --full_taxonomy   If enabled, will output full taxonomy as headers
                        instead of only current genus/species/whatever else.
```
