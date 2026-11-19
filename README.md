# PCB Assembly BOM and Placement Templates

Free CSV templates for preparing a bill of materials (BOM) and a pick-and-place file before you send a PCB assembly job to a factory.

Most delays on small PCBA builds start with the files: a fitted part with no manufacturer part number, a quantity that doesn't match the reference list, or a part marked DNP in one file and placed in the other. These templates use a layout that avoids those problems.

## Files

| File | What it is |
| --- | --- |
| `bom-template.csv` | Bill of materials, one row per line item |
| `placement-template.csv` | Pick-and-place (centroid) file, one row per placed part |

## BOM columns

| Column | Required | Notes |
| --- | --- | --- |
| Designator | Yes | Reference designators, comma-separated in quotes (`"R1,R2"`) |
| Quantity | Yes | Per board. Must equal the number of designators |
| Value | No | 10k, 100nF, and so on |
| Footprint | Yes | Package or footprint name, e.g. 0603, SOIC-8 |
| Manufacturer | Yes for fitted parts | |
| MPN | Yes for fitted parts | Manufacturer part number. Leave empty only for DNP rows |
| DNP | No | Write `DNP` for parts that are not fitted |
| Mount | Yes | `SMT`, `THT` or `Other` |
| Description | No | Free text |

## Placement columns

| Column | Notes |
| --- | --- |
| Designator | Must match the BOM |
| X (mm), Y (mm) | Part centre, in millimetres |
| Rotation | Degrees |
| Side | `Top` or `Bottom` |

Through-hole parts (J1 in the example) can be left out of the placement file.

## Checklist before you send files

- Every fitted line has a manufacturer and MPN
- Quantity equals the number of designators on that line
- DNP parts are marked in the BOM, and either removed from the placement file or clearly marked there
- Designators in the placement file match the BOM exactly (same case, no extra spaces)
- Placement coordinates and BOM come from the same design revision

## Check your files online

You can check a filled-in BOM and placement file with the free [BOM Checker](https://pcbapartner.com/tools/bom-checker/), or compare two BOM revisions with [BOM Compare](https://pcbapartner.com/tools/bom-compare/). Both run in the browser and do not upload your files.

A clean check only means the files are consistent. It does not verify footprints, polarity, pin 1 or part availability.

## About

Maintained by [PCBA Partner](https://pcbapartner.com), a PCB assembly manufacturer in Dongguan, China.

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Use, copy and change the templates freely, with no attribution required.
