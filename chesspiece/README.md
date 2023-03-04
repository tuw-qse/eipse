Case Study Chess Piece
----------------------

*Overview*. The *chess piece* product line originates from a [Pilotfabrik TU Wien - Industrie 4.0](https://www.pilotfabrik.at). In the project researchers investigated the production of the six types of chess pieces in the *Pilotfabrik TU Wien - Industrie 4.0*.

The real-world *chess piece* product line is produced in an academic production system, the *Pilotfabrik TU Wien - Industrie 4.0* at [Pilotfabrik TU Wien - Industrie 4.0](https://www.pilotfabrik.at). In the Pilot Factory at TU Wien research and testing is carried out to determine how the industry of tomorrow should look like. For this particular use case we consider a part of the Pilot Factory that has a portal, a cutting and turning machine, a Keyence quality control, a robot arm, an AGV, a 3D printer, and an assembly station. The setup can manipulate different products using and can be flexibly configured. The chess piece use case is of low complexity with six possible types and no dependencies between the features in the product structure itself.

*Data Collection*. A collaborating engineer and researcher (not an author of this paper) working at the Pilotfabrik created the use case for the machinery at the Pilotfabrik with colleagues providing us with the primary data for the case study. We received and discussed a different engineering artifacts, from CAD drawings of the products, over a detailed plans of the shop floor, to process sequence plans of the BPMN workflows. We analyzed the data manually extracting the information of the product line and its variants to derive the case study.

*Variability*. The *chess piece* product line consists of six variants that contain 3 parts. In particular, the chess pieces consist of a *base*, a *body*, and a threaded *rod* that connects these two parts. The *base* is produced from *aluminum bars* of 1m length on a *turning machine*. The *aluminum bar* is first *loaded into* the *turning machine* with a *bar loader*. Then the *turning machine* *cuts* the *aluminum bar* into the raw *bases* of suitable length for further processing. These *bases* are then *turned* on the *turning machine* to get their specific shape. Furthermore, the bases come in two versions. The king and the queen have the base with *two circumferential reamings* that are *carved into the aluminum*. The other chess pieces have a base that has *one reaming*. After their creation, the bases are measured with a *laser profiler* for turning accuracy. The *body* of the particular chess pieces is 3D-printed from \gls{pla* on an industrial *3D printer*. The *base* and the *body* each have a hole with a thread carved respectively printed in the middle. The threads each have a diameter for a standardized M6 *rod*.\footnote{ISO metric screw threads: [M2 threads](https://w.wiki/_wm23). Similarly to the base, the threaded *rod* comes in two versions, one with *20 millimeters* and one with *30 millimeters* in length. The *base*, the *body*, and the threaded *rod* are then assembled in an *assembly station*, where each individual part needs to be loaded into the station. Then, the parts need to be screwed together, where there are several possibilities of the process sequence.

*Configuration/Assembly*. The assembly sequence of the chess pieces has a particular process sequence in the production system but is relatively free except. For the production of the different variants, the same production resources are used. Therefore, we consider the case’s complexity to be at a low level.

*Summary* The complexity of the chess pieces product line with consists with six product variants is considered low.

Chess Piece Evaluation Guideline
--------------------------------
--------------------------------

The evaluation of the eIPSE approach was a user study that investigated the consistency of the approach utilizing the prototypically implemented toolchain. The assessed users, should step through the eIPSE process and evaluate the feasibility and usability of the approach and the tools.

## Prerequisites

- [Eclipse 2021-06](https://www.eclipse.org/downloads/packages/release/2021-06/r)
- [Eclipse FeatureIDE](https://featureide.github.io/)
- [Eclipse 4diac](https://www.eclipse.org/4diac/)
- eIPSE DM Editor
- V4rdiac

As a user, create a simple *Eclipse project* (`Ctrl+N > General > Project`) that can hold your eIPSE project data.
We refer to this folder as `<eclipse.project.folder>`.

## PPR-DSL (Step 1)

As a user, create a new *PPR-DSL* file (`Ctrl+N > General > File`) and open it with a text editor, ideally use [SublimeText](https://www.sublimetext.com/) with the provided ZIP for the code highlighting (not used during the actual evaluation task). The model shall represent three parts, which are (i) the partial and final products that should be manufactured by the production system, (ii) the atomic process steps that create the products with their required input products, predecessors, and resources, as well as (iii) the production resources that can execute a particular process required to manufacture a product.

### Products
For the chess piece use case, create partial products and final products in the *PPR-DSL*. Evaluation subjects should find out, which *partial products* they could group together using abstract parent products. Furthermore, they should define which of the partial products exclude each other because they are more or less supplemented by a similar partial product.

### Processes
As a user, investigate how you can assemble the partial products via specific *manufacturing* processes. Realize these atomic process steps in the *PPR-DSL* and, similar to the products. Group the processes based on their abstract products and exclude process steps that you deem unnecessary. Furthermore, examine which process steps in particular process step need to be direct predecessors and refer to them as needed in the required section.

### Resources
Resources are quite similar to products from the modeling perspective. For modeling them, as a user apply similar rules.

> If you replicate the study, copy the `chesspiece.dsl` file into the `<eclipse.project.folder>`.


## TAVART Transformation (Step 2)

As a user, use TRAVART to transform the model to the respective variability models. This can be done with the following command.

    java -jar jsstravart.jar <eclipse.project.folder>

The transformed models can be found in the `<eclipse.project.folder>`.

> If you replicate the study copy the content of the `variabilitymodels` folder to the `<eclipse.project.folder>`

## Product Configuration (Step 3)

As a user, take the `product_chesspiece.dsl.uvl` (product) feature model and copy it with the target name `model.uvl` (this is currently a bug in the *FeatureIDE*). Create a configuration file for the `model.uvl` with `Ctrl+N > FeatureIDE > Configuration File` and configure a product of your choice in the *Feature Model Configuration* view (cf. Figure 5 in the paper).

## Process Configuration (Step 4 & 5)

As a user, create a `.dconfig` (process) decision model configuration by right-clicking on the `process_dm_chesspiece.dsl.csv` file and choosing `DM Mapping > Generate Configuration File`. In the dialog choose a name and select the previously created and configured (product) feature model configuration. Reload the project editor to show the configuration. Open the file in the *Dopler DM* perspective and explore different production process sequence configurations by making the decisions in the editor. In case some production sequences do not suffice *rollback* the decision in the right pane of the DM editor (cf. Figure 6 in the paper).

## Resource Configuration (Step 6 to 8)

As a user, create a V4rdiac configuration in the V4rdiac perspective.
Validate the currently selected *product* and *process* variability models.
Configure the (resource) feature models and choose the number of instances (cf. Figure 7 in the paper).
On saving the configuration, the according function block diagrams should be created (cf. Figure 8 in the paper).
