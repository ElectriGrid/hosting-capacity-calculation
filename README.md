# Hosting capacity calculations

Recreating the hosting capacity calculations adapted from [Brockway et. al's (2021)](https://doi.org/10.1038/s41560-021-00887-6) methodology, which was found in [Supplementary Table 4](https://static-content.springer.com/esm/art%3A10.1038%2Fs41560-021-00887-6/MediaObjects/41560_2021_887_MOESM1_ESM.pdf). 

A comprehensive list of this project's data sources can be found on the [GitHub organization's README](https://github.com/ElectriGrid).

Additionally, customer type breakdown data from each utility was used in these calculations which we retrieved from:

1. SCE: In SCE's DRPEP online portal, we navigated to their public [ESRI API](https://drpep-sce2.opendata.arcgis.com/search), within the `ICA Tables` dataset, downloaded `ICA Single Consolidated Table`.

2. PG&E: In PG&E's [GRIPHubsite](https://grip.pge.com/), we selected & downloaded their `Distribution Lines (kV)` table within the comprehensive data table.

3. SDG&E: SDG&E does not publish a complete customer type breakdown in their online portal, though these data appear when clicking on ciruit segments on their [Interconnection Map](https://interconnectionmapsdge.extweb.sempra.com/). Instead, we gathered customer type breakdown manually for parts of SDG&E's service area and filled in any parts that were not gathered by proximity.

## Repository Structure

```
├── README.md
├── pge.ipynb
├── sce.ipynb
└── sdge.ipynb
```
## File descriptons

Each notebook, named after its respective utility, contains household-level hosting capacily calculations for generation capacity with and without operational flex, solar photovolatic with and without operational flex, and load capacity. 

To run this code, building point geometries (with information on the number of residential units) and ICA utility data is necessary.

## Variable outputs


| Variable                                 | Description                                                                                     |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------- |
| GEOID                                    | Census tract GEOID number for the 2020 census                                                   |
| geometry                                 | Census tract geometry in EPSG:3310 CRS                                                          |
| avg\_DER\_remain\_pv\_hh                 | Average remaining PV DER capacity per household in kilowatts (kW)                               |
| avg\_DER\_remain\_pv\_opflex\_hh         | Average remaining PV DER capacity per household with operational flex in kilowatts (kW)         |
| avg\_DER\_remain\_generation\_hh         | Average remaining generation DER capacity per household in kilowatts (kW)                       |
| avg\_DER\_remain\_generation\_opflex\_hh | Average remaining generation DER capacity per household with operational felx in kilowatts (kW) |
| avg\_DER\_total\_generation\_hh          | Average total generation DER per household in kilowatts (kW)                                    |
| avg\_DER\_remain\_load\_hh               | Average remaining load capacity per household in kilowatts (kW)                                 |
| avg\_DER\_total\_pv\_hh                  | Average total PV DER per household in kilowatts (kW)                                            |
| zillow\_tract\_hh\_count                 | Zillow homes count                                                                              |

## Contributors
- [Sofia Sarak](https://github.com/sofiasarak)
- [Sofia Rodas](https://github.com/sofiiir)
- [Zach Loo](https://github.com/zachyyy700)

The analysis is part of a larger capstone project for the [Master of Environmental Data Science program](https://bren.ucsb.edu/masters-programs/master-environmental-data-science) at the Bren School of Environmental Science & Management. More information on the project can be found on the [Bren website](https://bren.ucsb.edu/projects/power-lines-and-people-mapping-how-distribution-grid-constraints-shape-resilient-and).
