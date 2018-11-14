# Crafting Blocks 

*Source file: io/anuke/mindustry/content/blocks/CraftingBlocks.java*

Production Rate (PR) and Fuel Consumption Rate (FR) are max-per-sec values **which assume your TPS is 60**.

| Name                  | HP  | Size | Power Use  | Input           | Flux | Output               | Base PR |
|-----------------------|-----|------|------------|-----------------|------|----------------------|---------|
| Smelter               | 70  | 2x2  | N/A        | 1CP 2LE 1CO     | 1    | DA                   | 1.33    | 
| Arc Smelter           | 90  | 2x2  | 0.1        | 1CP 2LE         | 2    | DA                   | 2       |
| Silicon Smelter       | 90  | 2x2  | 0.05       | 2SA 1CO         | N    | SI                   | 1.5     | 
| Plastanium Compressor | 320 | 2x2  | 0.3        | 2TI .25OI       | N    | PL                   | 1       | 
| Phase Weaver          | 160 | 2x2  | 0.5        | 10SA 4TH        | N    | PF                   | 0.5     | 
| Alloy Smelter         | 160 | 2x2  | 0.4        | 3CP 4LE 2TI 3SI | 3    | SU                   | 0.8     | 
| Cryofluid Mixer       | 160 | 2x2  | 0.1        | 1TI .3WA        | N    | CF                   | 1.2     | 
| Pyratite Mixer        | 160 | 2x2  | 0.02       | 1SA 2LE 1CO     | N    | PY                   | 3       | 
| Blast Mixer           | 60  | 2x2  | 0.04       | 1PY .05OI       | N    | BC                   | 3       | 
| Melter                | 200 | 1x1  | 0.1        | 1ST             | N    | LV                   | 0.12    | 
| Separator             | 50  | 1x1  | N/A        | 2ST             | N    | ST SA CP LE CO TI    | 1.5     |
| Centrifuge            | 200 | 2x2  | 0.2        | 2ST .5WA        | N    | ST SA CP LE CO TI TH | 4       |
| Biomatter Compressor  | 320 | 2x2  | 0.06       | 1BM             | N    | OI                   | 0.62    |
| Pulverizer            | 80  | 1x1  | 0.05       | 1ST             | N    | SA                   | 1.5     |
| Solidifier            | 80  | 1x1  | N/A        | 1LV             | N    | ST                   | 4.28    |
| Incinerator           | 90  | 1x1  | 0.05       | All             | N    | N/A                  | N/A     |