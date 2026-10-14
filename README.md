# pyssporg

Python tooling for the [SSP (System Structure and Parameterization) standard](https://ssp-standard.org), FMI co-simulation, and SysML v2.

Our libraries let you create, inspect, and edit SSP packages; simulate them across interchangeable engines and compare the results; bridge SysML v2 architectures to SSP/FMI artifacts; and turn CSV signals into FMUs. Most repos are MIT-licensed Python; one ships a C++ runtime.

## Repositories

| Repository | Language | Description |
| --- | --- | --- |
| [pyssp_standard](https://github.com/pyssporg/pyssp_standard) | Python | Core library to interact with files specified by the SSP standard. Create, read, and edit SSV, SSM, and SSB files; read SSP, FMU, and SSD files. Also supports the SRMD standard. |
| [pyssp_simulate](https://github.com/pyssporg/pyssp_simulate) | Python | Simulate SSP packages through a single interface with pluggable engines — FMPy (default), OMSimulator, ssp4sim, and cosim — and compare results across engines. |
| [ssp_references](https://github.com/pyssporg/ssp_references) | Python | Curated SSP model fixtures plus the scripts used to prepare them, simulate them, and compare results across engines. |
| [pyssp_sysml2](https://github.com/pyssporg/pyssp_sysml2) | Python | Generate SSP, FMI, and SysML artifacts from a SysML v2 architecture or SSD, and sync SSD wiring changes back into SysML. |
| [pysysml2_cps](https://github.com/pyssporg/pysysml2_cps) | Python | Parse a practical subset of SysML v2 text files into a connected in-memory model for Python tooling (parts, ports, attributes, requirements, connections). |
| [pyfmu_csv](https://github.com/pyssporg/pyfmu_csv) | Python + C++ | Generate FMI 2.0 Co-Simulation FMU packages from CSV-described signals, with a C++ runtime embedded in the FMU. |

## Where to Start

- **Working with SSP files in Python** — start with [`pyssp_standard`](https://github.com/pyssporg/pyssp_standard), the foundation the other tools build on.
- **Simulating an SSP package** — install [`pyssp_simulate`](https://github.com/pyssporg/pyssp_simulate); the default FMPy backend works out of the box, and additional engines are opt-in extras.
- **Looking for example models** — see the reference fixtures in [`ssp_references`](https://github.com/pyssporg/ssp_references).
- **Coming from a SysML v2 architecture** — use [`pyssp_sysml2`](https://github.com/pyssporg/pyssp_sysml2) to generate SSD, SSV, and FMI artifacts, or [`pysysml2_cps`](https://github.com/pyssporg/pysysml2_cps) to parse SysML v2 directly.
- **Turning CSV data into an FMU** — use [`pyfmu_csv`](https://github.com/pyssporg/pyfmu_csv).

## Ecosystem

The tools interoperate with engines and standards from the wider co-simulation community: [FMPy](https://pypi.org/project/FMPy/), [OMSimulator](https://pypi.org/project/OMSimulator/) (OpenModelica), [ssp4sim](https://github.com/jkCXf9X4/ssp4sim), [cosim](https://github.com/open-simulation-platform/cosim-cli) (Open Simulation Platform), and the [FMI](https://fmi-standard.org) and [SSP](https://ssp-standard.org) standards.

## License

Most repositories are MIT-licensed — see the `LICENSE` file in each repo.
