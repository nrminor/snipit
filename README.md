# snipit
Summarise nucleotide or amino acid changes relative to a reference sequence. 

_Note:_ This fork is a modification of _snipit_ version 1.0.3, which enables visualization of amino acid changes and nucleotide changes. It will not work if you have previous installations of _snipit_ on your system. For support running the original `snipit` program, please visit the original repository at [github.com/aineniamh/snipit](https://github.com/aineniamh/snipit). Install the _snipit_ version from before our modifications with `pip install snipit==1.0.3`.


<img src="./docs/genome_graph.png" width="700">

### Usage
```
usage: snipit <alignment> [options]

snipit

positional arguments:
  alignment             Input alignment fasta file

optional arguments:
  -h, --help            show this help message and exit
  -r REFERENCE, --reference REFERENCE
                        Indicates which sequence in the alignment is the reference (by sequence ID). Default:
                        first sequence in alignment
  -l LABELS, --labels LABELS
                        Optional csv file of labels to show in output snipit plot. Default: sequence names
  --l-header LABEL_HEADERS
                        Comma separated string of column headers in label csv. First field indicates sequence
                        name column, second the label column. Default: 'name,label'
  -d OUTPUT_DIR, --output-dir OUTPUT_DIR
                        Output directory. Default: current working directory
  -o OUTFILE, --output-file OUTFILE
                        Output file name stem. Default: snp_plot
  -f FORMAT, --format FORMAT
                        Format options (png, jpg, pdf, svg, tiff) Default: png
  --height HEIGHT       Overwrite the default figure height
  --width WIDTH         Overwrite the default figure width
  --size-option SIZE_OPTION
                        Specify options for sizing. Options: expand, scale
  --flip-vertical       Flip the orientation of the plot so sequences are below the reference rather than
                        above it.
  --include-positions INCLUDED_POSITIONS [INCLUDED_POSITIONS ...]
                        One or more range (closed, inclusive; one-indexed) or specific position only included
                        in the output. Ex. '100-150' or Ex. '100 101' Considered before '--exclude-
                        positions'.
  --exclude-positions EXCLUDED_POSITIONS [EXCLUDED_POSITIONS ...]
                        One or more range (closed, inclusive; one-indexed) or specific position to exclude in
                        the output. Ex. '100-150' or Ex. '100 101' Considered after '--include-positions'.
  --exclude-ambig-pos   Exclude positions with ambig base in any sequences. Considered after '--include-
                        positions'
  --sort-by-mutation-number
                        Render the graph with sequences sorted by the number of SNPs relative to the
                        reference (fewest to most). Default: False
  --high-to-low         If sorted by mutation number is selected, show the sequences with the fewest SNPs
                        closest to the reference. Default: False
  -c COLOUR_PALETTE, --colour-palette COLOUR_PALETTE
                        Specify colour palette. Options: primary, classic, purine-pyrimidine, greyscale, wes,
                        verity
```

### Install

To install this version of `snipit`, be sure to remove any previous installations of `snipit` with `pip uninstall snipit` and/or `conda uninstall snipit`. Next, we recommend you clone this repo into a working directory of your choice. In that directory, run the following:

```
python3 setup.py install
```

To double check it installed, run `snipit -v`. You may also choose to run `which snipit` to make sure it was installed somewhere reasonable.
