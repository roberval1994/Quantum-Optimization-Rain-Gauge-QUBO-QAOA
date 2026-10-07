# Data access / Acesso aos dados

Some datasets are **too large to version on GitHub** (notably the WorldPop raster,
~457 MB, which exceeds GitHub's 100 MB per-file limit) and are **not** included here.
This guide explains how to obtain each source and where to place it.

Alguns conjuntos de dados são **grandes demais para versionar no GitHub** (em especial o
raster do WorldPop, ~457 MB, acima do limite de 100 MB por arquivo) e **não** estão
incluídos aqui. Este guia explica como obter cada fonte e onde colocá-la.

## Expected layout / Estrutura esperada

```
data/
├── worldpop/
│   └── bra_pop_2025_CN_100m_R2025A_v1.tif   # download manually (see below)
├── shapefiles/                               # study-area boundaries (pddmap_so.*)
├── monthly/                                  # monthly datasets (01.xlsx ... 12.xlsx)
└── locations/                                # candidate station locations
```

## Sources / Fontes

| Dataset | Source | How to get it |
|---|---|---|
| **Population** (100 m raster) | [WorldPop](https://www.worldpop.org/) — Brazil, Constrained, 2025, R2025A | Download `bra_pop_2025_CN_100m_R2025A_v1.tif` into `data/worldpop/`. |
| **Study-area shapefiles** | Prefeitura de São José dos Campos / GeoSanja | Boundary and risk layers (`.shp/.dbf/.prj/.shx`). |
| **Monthly rainfall** | PlugField (2025) | Monthly rain-gauge spreadsheets. |

## Note on quantum backends / Nota sobre backends quânticos

Running QAOA on real hardware requires a free [IBM Quantum](https://quantum.ibm.com/)
account and API token. Never commit your token — it is covered by `.gitignore`.

Executar o QAOA em hardware real requer conta gratuita na
[IBM Quantum](https://quantum.ibm.com/) e um token de API. Nunca faça commit do seu token
— ele já está coberto pelo `.gitignore`.
