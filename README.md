# Extended Iterative Process Sequence Exploration (eIPSE)

This repository contains the accompanying material to the paper __Variability Modeling of Products, Processes, and Resources in Cyber-Physical Production Systems Engineering__.

Cyber-Physical Production Systems (CPPSs), such as automated car plants, execute a configurable sequence of production steps to manufacture products from a product portfolio. In CPPS engineering, domain experts start with manually determining feasible production step sequences and resources based on implicit knowledge. This process is hard to reproduce and highly inefficient. 

This paper presents the __Extended Iterative Process Sequence Exploration (eIPSE)__ to derive variability models for products, processes, and resources from a domain-specific description. To automate the integrated exploration and configuration process of the CPPS, we provide editor support which reduces the configuration space and allows for automatically generating CPPS artifacts, such as control code for resources. We evaluate the approach with real-world use cases and collect feedback from engineers from different backgrounds. The results confirm the usefulness of the eIPSE approach and accompanying prototype, which allows easy configuring of a desired CPPS.

## Organization of the repository

The repository contains five use cases:

- [Chesspiece](chesspiece) by courtesy of [Pilotfabrik TU Wien - Industrie 4.0](https://www.pilotfabrik.at)
- [Truck](truck) by courtesy of [Tu Prague](https://testbed-test.ciirc.cvut.cz)
- [Shift fork](shiftfork) by courtesy of our industry partner
- [Rocker switch](rockerswitch) by courtesy of our industry partner
- [Waterfilter](waterfilter) by courtesy of [Askwar Hilonga](https://gongali.wordpress.com/the-water-nanofilter/)

Every use case contains the following artifacts:

- a README.md for detailed information on the use case
- a `*.dsl` file that contains the PPR-DSL definition file for the products, processes, and resources
- a folder that contains the variability models transformed by TRAVAT
- a folder that contains the V4rdiac projects

The repository also contains a folder that contains the evaluation material:

- the *PPR-DSL* [cheatsheet](evaluation.material/Cheatsheet.pdf)
- the SublimeText settings [evaluation.material/sublime.settings](evaluation.material/sublime.settings) that contains code highlighting and completion snippets for [SublimeText](https://www.sublimetext.com/) that need to be copied to `USER/.config/sublime-text/Packages/User/`.
