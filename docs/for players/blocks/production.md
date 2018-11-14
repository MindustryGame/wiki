# Mindustry Docs

## Production Blocks

*Source file: io/anuke/mindustry/content/blocks/ProductionBlocks.java*

Production Rate (PR) are max-per-sec values **which assume your TPS is 60**.

A name enclosed in ? is experimental and only a concept hidden in code.

### Drills

For Drills, Liquid-Boosted PR can be calculated by multiplying the Base PR by 2.6.

| Name                  | Size | Power Use | Base PR | Drillables
|-----------------------|------|-----------|---------|-----------
| Mechanical Drill      | 2x2  | N/A       | 0.2     |    SA CP LE CO
| Pneumatic Drill       | 2x2  | N/A       | 0.25    | ST SA CP LE CO TI 
| Laser Drill           | 2x2  | .11       | 0.42    | ST SA CP LE CO TI TH
| Airblast Drill        | 3x3  | .3        | 1       | ST SA CP LE CO TI TH
| ? Plasma Drill ?      | 4x4  | .7        | 1.2     | ST SA CP LE CO TI TH

### Miscellaneous

| Name                  | Size | Power Use | Base PR | Input | Output | Place On
|-----------------------|------|-----------|---------|-------|--------|---------
| Water Extractor&nbsp; | 2x2  | .09       | 3.9     |       | W      | Any
| Oil Extractor*        | 3x3  | .3        | 5.4     | W, SA | O      | Any
| Cultivator            | 2x2  | .08       | 0.23    | W     | BM     | Grass