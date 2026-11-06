# pyssporg

Python tooling for the [SSP (System Structure and Parameterization) standard](https://ssp-standard.org), FMI co-simulation, and SysML v2.

Our libraries let you create, inspect, and edit SSP packages; simulate them across interchangeable engines and compare the results; bridge SysML v2 architectures to SSP/FMI artifacts; turn CSV signals into FMUs; wrap Model Exchange FMUs into Co-Simulation FMUs; and run verification-and-validation workflows over the whole chain. Most repos are MIT-licensed Python; one grows a C++/C runtime.

## Repositories

### Core & foundation

| Repository | Language | Description |
| --- | --- | --- |
| [pyssp_standard](https://github.com/pyssporg/pyssp_standard) | Python | Core library to interact with files specified by the SSP standard. Create, read, and edit SSV, SSM, and SSB files; read SSP, FMU, and SSD files. Also supports the SRMD standard. |
| [experimental_pyssp_standard](https://github.com/pyssporg/experimental_pyssp_standard) | Python | Experimental fork of `pyssp_standard` with refactored SSP/FMI model APIs for the pyssp ecosystem. Under active development; not a release line. |

### Simulation, verification & validation

| Repository | Language | Description |
| --- | --- | --- |
| [pyssp_simulate](https://github.com/pyssporg/pyssp_simulate) | Python | Simulate SSP packages through a single interface with pluggable engines — FMPy (default), OMSimulator, ssp4sim, and cosim — and compare results across engines. |
| [ssp_references](https://github.com/pyssporg/ssp_references) | Python | Curated SSP model fixtures plus the scripts used to prepare them, simulate them, and compare results across engines. |
| [pyssp_vv](https://github.com/pyssporg/pyssp_vv) | Python | Verification and validation for simulation models: measurement (series, alignment, metrics, coverage, normalisation) and judgment (criteria, dispositions, verdicts), linked by policy and evidenced by reports. |
| [pyssp_workflow](https://github.com/pyssporg/pyssp_workflow) | Python | Composable workflows for building, running, comparing, verifying, and validating SSP models — as plain functions and as node-ready work units. Composes `pyssp_standard`, `pyssp_simulate`, `pyssp_vv`, and `pyssp_sysml2`; owns none of them. |
| [pylsuq](https://github.com/pyssporg/pylsuq) | Python | Python implementation of the LS-UQ (Uncertainty Quantification) standard developed as part of the OpenSCALING project. Loads and saves LS-UQ XML documents via a dataclass-based XML-to-Python mapping. |

### SysML v2 bridging

| Repository | Language | Description |
| --- | --- | --- |
| [pyssp_sysml2](https://github.com/pyssporg/pyssp_sysml2) | Python | Generate SSP, FMI, and SysML artifacts from a SysML v2 architecture or SSD, and sync SSD wiring changes back into SysML. |
| [pycps_sysml2](https://github.com/pyssporg/pycps_sysml2) | Python | The SysML dialect layer for CPS artifacts: parses SysML v2 into a repo-owned IR and owns variation, selection, constraints, and every marker and metadata accessor for the SSP and FMI dialects. |
| [pyfmi_sysml2](https://github.com/pyssporg/pyfmi_sysml2) | Python | Generate FMI 2.0 Co-Simulation artifacts from a SysML v2 architecture: `modelDescription.xml`, C interface headers, Modelica connectors, and a packaged `.fmu`. |

### FMU & packaging

| Repository | Language | Description |
| --- | --- | --- |
| [pyfmu_csv](https://github.com/pyssporg/pyfmu_csv) | Python + C++ | Generate FMI 2.0 Co-Simulation FMU packages from CSV-described signals, with a C++ runtime embedded in the FMU. |
| [pyfmi_me_to_cs](https://github.com/pyssporg/pyfmi_me_to_cs) | Python + C | Convert a complete SSP package (`.ssp`) — one or more FMI 2.0 Model Exchange FMUs wired together in a `SystemStructure.ssd` — into a single FMI 2.0 Co-Simulation FMU (`.fmu`), with a C wrapper and a local solver. |

## Where to Start

- **Working with SSP files in Python** — start with [`pyssp_standard`](https://github.com/pyssporg/pyssp_standard), the foundation the other tools build on.
- **Simulating an SSP package** — install [`pyssp_simulate`](https://github.com/pyssporg/pyssp_simulate); the default FMPy backend works out of the box, and additional engines are opt-in extras.
- **Looking for example models** — see the reference fixtures in [`ssp_references`](https://github.com/pyssporg/ssp_references).
- **Verifying and validating a model** — measure and judge simulation results with [`pyssp_vv`](https://github.com/pyssporg/pyssp_vv), or compose a full build–run–compare–validate chain with [`pyssp_workflow`](https://github.com/pyssporg/pyssp_workflow).
- **Coming from a SysML v2 architecture** — use [`pyssp_sysml2`](https://github.com/pyssporg/pyssp_sysml2) to generate SSD, SSV, and FMI artifacts; [`pycps_sysml2`](https://github.com/pyssporg/pycps_sysml2) is the shared SysML dialect layer, and [`pyfmi_sysml2`](https://github.com/pyssporg/pyfmi_sysml2) targets FMI artifacts directly.
- **Packaging models as FMUs** — turn CSV data into an FMU with [`pyfmu_csv`](https://github.com/pyssporg/pyfmu_csv), or wrap Model Exchange FMUs into a single Co-Simulation FMU with [`pyfmi_me_to_cs`](https://github.com/pyssporg/pyfmi_me_to_cs).
- **Uncertainty quantification** — work with LS-UQ documents via [`pylsuq`](https://github.com/pyssporg/pylsuq).

## Ecosystem

The tools interoperate with engines and standards from the wider co-simulation community: [FMPy](https://pypi.org/project/FMPy/), [OMSimulator](https://pypi.org/project/OMSimulator/) (OpenModelica), [ssp4sim](https://github.com/jkCXf9X4/ssp4sim), [cosim](https://github.com/open-simulation-platform/cosim-cli) (Open Simulation Platform), and the [FMI](https://fmi-standard.org) and [SSP](https://ssp-standard.org) standards.

## License

Most repositories are MIT-licensed — see the `LICENSE` file in each repo.