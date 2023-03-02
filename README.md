# Extended Iterative Process Sequence Exploration (eIPSE)

This repository contains the accompanying material to the paper __Variability Modeling of Products, Processes, and Resources in Cyber-Physical Production Systems Engineering__.

Cyber-Physical Production Systems (CPPSs), such as automated car plants, execute a configurable sequence of production steps to manufacture products from a product portfolio. In CPPS engineering, domain experts start with manually determining feasible production step sequences and resources based on implicit knowledge. This process is hard to reproduce and highly inefficient. 

In this paper, we present the __Extended Iterative Process Sequence Exploration (eIPSE)__ to derive variability models for products, processes, and resources from a domain-specific description. To automate the integrated exploration and configuration process of the CPPS, we provide editor support which reduces the configuration space and allows for automatically generating CPPS artifacts, such as control code for resources. We evaluate the approach with real-world use cases and collect feedback from engineers from different backgrounds. The results confirm the usefulness of the eIPSE approach and accompanying prototype which allow to straightforwardly configure a desired CPPS.

## Organization of the repository

The repository contains five use cases:

- [Chesspiece](shiftfork) by [Pilotfabrik TU Wien - Industrie 4.0](https://www.pilotfabrik.at)
- [Truck](truck) by [Tu Prague](https://testbed-test.ciirc.cvut.cz)
- [Shift fork](shiftfork) by our industry partner
- [Rocker switch](rockerswitch) by our industry partner
- [Waterfilter](waterfilter) by [Askwar Hilonga](https://gongali.wordpress.com/the-water-nanofilter/)

Every use case contains the following artifacts:

- a README.md for iInformation about the use case
- a `*.dsl` file that contains the PPR-DSL definition file
- a folder that contains the variability models transformed by TRAVAT
- a folder that contains the V4rdiac projects
