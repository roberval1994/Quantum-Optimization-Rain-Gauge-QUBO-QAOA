# Otimização Quântica de Redes de Pluviômetros (QUBO / QAOA)

**Formulação da localização de pluviômetros como QUBO e resolução com QAOA, comparada a solvers clássicos**

🌐 **Idioma / Language:** **Português** | [English](README.md)

---

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Qiskit](https://img.shields.io/badge/Qiskit-6929C4.svg?logo=qiskit&logoColor=white)](https://www.ibm.com/quantum/qiskit)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-pesquisa-blueviolet.svg)]()

> Parte da pesquisa de doutorado em Pesquisa Operacional na **UNIFESP / ITA**.
> Veja a visão geral da pesquisa: [PhD-Research-Operational-Research](https://github.com/roberval1994).

## Visão geral

Este projeto formula a **alocação ótima de estações pluviométricas** como um problema de
**Otimização Binária Quadrática Sem Restrições (QUBO)** e o resolve com o
**Algoritmo de Otimização Aproximada Quântica (QAOA)**, comparando os resultados com
solvers clássicos exatos e heurísticos.

O estudo investiga se a otimização quântica (e quântico-inspirada) consegue igualar ou se
aproximar das soluções clássicas em um problema real de localização espacial de facilidades.

## Abordagem

1. **Modelagem do problema** — o problema de cobertura/alocação é codificado como QUBO, com reformulação por penalidades das restrições de cobertura.
2. **Calibração** — o coeficiente de penalidade (`λ`) é calibrado para que soluções factíveis dominem o cenário de energia.
3. **Solver quântico** — QAOA executado via **Qiskit** (simulador e/ou backends IBM Quantum), com análise do comportamento de profundidade/threshold do QAOA.
4. **Baselines clássicos** — solvers exatos e heurísticos (incluindo processamento de grid baseado em IDW) para comparação.
5. **Benchmark** — comparação de solvers em qualidade, escalabilidade e tempo de execução.

## Estrutura do repositório

```
.
├── notebooks/
│   ├── QUBO_Rain_Gauge_Optimization.ipynb    # Pipeline principal QUBO/QAOA (versão mais recente)
│   └── celulas_amclp_analise.ipynb           # Análise AMCLP no nível de célula
├── data/                                     # Dados mensais, raster de população, shapefiles
├── results/                                  # Tabelas comparativas (.csv/.xlsx), resultados dos solvers
├── figures/                                  # Calibração, escalabilidade, threshold do QAOA, mapas
├── requirements.txt
├── LICENSE
├── README.md                                 # Inglês
└── README.pt-BR.md                           # Português (este arquivo)
```

## Dados

> **Dados pesados** (ex.: o raster de população WorldPop, ~457 MB) **não são versionados**
> neste repositório. Veja [`data/README.md`](data/README.md) para instruções de download,
> fontes (WorldPop, GeoSanja/SJC, PlugField) e a estrutura esperada de pastas.

## Como começar

```bash
git clone https://github.com/roberval1994/Quantum-Optimization-Rain-Gauge-QUBO-QAOA.git
cd Quantum-Optimization-Rain-Gauge-QUBO-QAOA

python -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # Linux / macOS
pip install -r requirements.txt

jupyter notebook
```

> A execução em hardware real da IBM Quantum requer conta gratuita na
> [IBM Quantum](https://quantum.ibm.com/) e um token de API. Os notebooks também rodam no
> simulador local Qiskit Aer.

## Principais resultados

- Formulação QUBO ponta a ponta de um problema real de alocação de pluviômetros.
- Calibração da penalidade `λ` garantindo factibilidade.
- Comparação entre solvers clássicos e quânticos (qualidade, escalabilidade, tempo).
- Figuras reprodutíveis: curva de calibração, escalabilidade, threshold do QAOA, mapas comparativos.

## Tecnologias

`Python` · `Qiskit` · `IBM Quantum` · `NumPy` · `pandas` · `GeoPandas` · `Matplotlib` · `Folium`

## Autor

**Roberval Gonçalves Moreira Filho**
Cientista de Dados | Analista de Pesquisa Operacional — Doutorando, UNIFESP/ITA

[![Email](https://img.shields.io/badge/Email-roberval.researcher.or%40outlook.com-red)](mailto:roberval.researcher.or@outlook.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-robervalOr-blue)](https://www.linkedin.com/in/robervalOr)
[![GitHub](https://img.shields.io/badge/GitHub-roberval1994-black)](https://github.com/roberval1994)

## Licença

Distribuído sob a Licença MIT. Veja [LICENSE](LICENSE).
