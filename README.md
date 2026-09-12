# Awesome Fly [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated collection of fruit fly connectome projects, from Doom and desktop pets to brain models, biomechanical bodies, and research tools.

Explore what people are building with **MaleCNS**, **FlyWire**, and the *Drosophila melanogaster* connectome. Each entry links to its creators' repository and explains what it actually offers.

Start with a [game](#games-and-control-experiments), explore a [desktop fly](#desktop-flies-and-interactive-worlds), or build your own using the [research foundations](#brain-models-and-embodied-simulation).

Contributions welcome: [suggest a project](https://github.com/cobanov/awesome-fly/issues/new?template=add-project.yml) or send a pull request. Read the [contribution guide](CONTRIBUTING.md).

## Contents

- [Start here](#start-here)
- [Games and control experiments](#games-and-control-experiments)
- [Desktop flies and interactive worlds](#desktop-flies-and-interactive-worlds)
- [Language, art, and other experiments](#language-art-and-other-experiments)
- [Brain models and embodied simulation](#brain-models-and-embodied-simulation)
- [Datasets and official resources](#datasets-and-official-resources)
- [Analysis libraries and viewers](#analysis-libraries-and-viewers)
- [Tutorials and papers](#tutorials-and-papers)
- [Related lists](#related-lists)
- [Contributing](#contributing)

## Start here

A **connectome** records neurons and their connections. A simulation adds assumptions about neuron dynamics, sensory input, and motor output. A moving fly, changing weights, or a game demo does not by itself demonstrate biological fidelity or learned behavior.

- **MaleCNS** covers the adult male central nervous system, including brain and ventral nerve cord. The official project dates v1.0 to **June 8, 2026** and the Cell paper to **September 3, 2026**. [Project and release history](https://male-cns.janelia.org/).
- **FlyWire / FAFB** is an adult female **brain** connectome, a different dataset from MaleCNS. [FlyWire](https://flywire.ai/).
- **Flybody** and **NeuroMechFly** supply simulated bodies and environments. Using either does not automatically connect a brain model to the body.

**Reading the list:** community entries summarize their authors' documentation, reviewed on **September 12, 2026**. These are source reviews, not independent reproductions. **Prototype**, **circuit subset**, and **release pending** identify useful limitations. Neuron counts depend on the release and filtering; synaptic contacts and directed neuron-pair connections are different quantities.

## Games and control experiments

- [Doomfly](https://github.com/nftechie/doomfly) by **nftechie** - MaleCNS simulation connected to ViZDoom through modeled visual inputs and a fixed button readout. Includes plasticity experiments and negative validation results; learned survival has not been demonstrated.
- [Fly64](https://github.com/ornata/fly) by **ornata** - Hooks a MaleCNS model up to Super Mario 64, with a local dashboard and macOS setup. A playful experimental controller; requires your own game ROM.
- [Flyhard](https://github.com/MarkUnthank/flyhard) by **MarkUnthank** - Trains a MaleCNS-based model to operate a steering wheel through simulated fly limbs and connect it to CARLA. Documents a bounded steering result; visual driving remains a future milestone.
- [Help the Fly Escape](https://github.com/dzhng/fly-escape) by **dzhng** - Arrange household objects and observe flies navigating a 3D browser game. Rust/WASM simulation using a **selected MaleCNS circuit**. [Play](https://fly-escape.vercel.app/).
- [Swat](https://github.com/hrook1/Swat) by **hrook1** - Browser arcade game with a visible escape circuit: 6,000 MaleCNS neurons influence evasive movement alongside authored game mechanics. **Circuit subset.** [Play](https://fruitfly-tiny-brain.vercel.app/).
- [FlyBrain](https://github.com/Jhongdlp/FlyBrain) by **Jhongdlp** - MaleCNS-based game-boss experiment with a Rust neural engine, Python training environment, and Three.js viewer.
- [Fly Chess Lab](https://github.com/tolatolatop/fly-chess) by **tolatolatop** - FlyWire chess experiment with a Rust/WASM LIF simulation, spike traces, and disconnection controls. Uses an engineered, currently untrained move readout. [Demo](https://tolatolatop.github.io/fly-chess/).
- [fly-craftax](https://github.com/liuzihe02/fly-craftax) by **liuzihe02** - Connectome simulation connected to Craftax, with PPO training of a descending-neuron readout, baseline comparisons, and a replay viewer. **Research prototype.**
- [PinFly](https://github.com/cobanov/pinfly) by **cobanov** - Pinball workbench with Flybody geometry and a viewer for 18 MaleCNS neuron morphologies. **Interface prototype:** activity is deterministic; connectome execution and reinforcement learning are planned.
- [NeuroCraft Fly](https://github.com/evnsnclr/neurocraft-fly-public) by **evnsnclr** - Minecraft project with a recorded MaleCNS-based interactive demo and a release roadmap. **Release pending:** the public repository currently contains project materials, not runnable mod or companion source.

## Desktop flies and interactive worlds

- [DesktopFly](https://github.com/DenisSergeevitch/desktop-fly) by **DenisSergeevitch** - A macOS desktop fly combining FlyWire spiking circuits with a MaleCNS brain-to-leg extract, modeled senses, and articulated behavior. Includes an Electron port.
- [gnat](https://github.com/lubabs770/gnat) by **lubabs770** - Linux/Hyprland desktop port of DesktopFly with a brain window and stimulation controls. Uses a **668-neuron circuit subset**.
- [FlyBrain](https://github.com/snedea/flybrain) by **snedea** - Browser-based FlyWire FAFB v783 LIF simulation with food, touch, light, and temperature inputs and a live neural activity display.
- [FlyWire Neuro](https://github.com/pusulamkendim/flywire-neuro) by **pusulamkendim** - Local FlyWire LIF simulation linked to a persistent 3D body, sensory controls, and recorded runs. Descending-neuron activity selects measured or cached motor behavior. **Research prototype.**
- [Infinite Sugar](https://github.com/cnqso/infinite-sugar) by **cnqso** - Browser artwork placing a FlyWire-based fly in a terrarium with continuous sweet-sensing input. Neural activity drives some movements while wings and small foot motions use supplied patterns. [Experience](https://infinitesugar.cnqso.com/).

## Language, art, and other experiments

- [FLM](https://github.com/nftechie/flm) by **nftechie** - Frozen language model coupled to the retained MaleCNS graph through a trained readout adapter. Language ability comes from the pretrained language model.
- [Fly / Wirehead](https://github.com/mattyhempstead/fly-wirehead) by **mattyhempstead** - A MaleCNS simulation receives frames from insect videos on a virtual phone. Local Python/C++ simulation, browser observation chamber, and neural telemetry.
- [Stonkfly](https://github.com/nftechie/stonkfly) by **nftechie** - Experimental MaleCNS controller with market-chart inputs, paper trading, and optional Coinbase integration. Includes modeled reinforcement and memory; profitable learning has not been demonstrated.
- [Faiku](https://github.com/xyzzyapps/faiku) by **xyzzyapps** - Haiku and glyph-tracing experiment using MaleCNS simulation and mushroom-body-inspired reinforcement, with a separate reduced fallback model.
- [mindmeld-with-fly](https://github.com/Decentricity/mindmeld-with-fly) by **Decentricity** - Sparse MaleCNS reservoir experiments with terminal rendering and recording/replay. **Prototype:** the README places the EEG interface in a future phase.

## Brain models and embodied simulation

- [Drosophila brain model](https://github.com/philshiu/Drosophila_brain_model) by **philshiu and collaborators** - Research code for the Shiu et al. connectome-based leaky integrate-and-fire model, including activation/silencing experiments, notebooks, and FlyWire data configuration.
- [fly-brain](https://github.com/eonsystemspbc/fly-brain) by **Eon Systems** - FlyWire whole-brain LIF implementation based on Shiu et al., with multiple simulation backends and benchmarking tools. This repository supplies the neural model; it is not a complete embodied demo package.
- [flybody](https://github.com/TuragaLab/flybody) by **TuragaLab / Google DeepMind / HHMI Janelia** - Anatomically detailed MuJoCo fruit-fly body, walking and flight environments, and reinforcement-learning examples. A body and control platform.
- [FlyGym / NeuroMechFly](https://github.com/NeLy-EPFL/flygym) by **NeLy-EPFL** - Python framework for embodied sensorimotor experiments with a biomechanical fly, sensory interfaces, and physical environments. Check version-specific documentation when following older tutorials.
- [flyvis](https://github.com/TuragaLab/flyvis) by **TuragaLab** - PyTorch implementation of connectome-constrained models of the fly visual system, with pretrained models and analysis tutorials.
- [Embodied fly-brain](https://github.com/erojasoficial-byte/fly-brain) by **erojasoficial-byte** - Community research repository combining a FlyWire spiking model with NeuroMechFly/MuJoCo, sensory experiments, and an accompanying preprint.

## Datasets and official resources

- [MaleCNS](https://male-cns.janelia.org/) - Official male CNS project, cell-type exploration, release history, and [downloads](https://male-cns.janelia.org/download/). Collaboration between FlyEM/HHMI Janelia, Cambridge, MRC LMB, and Google Research.
- [MaleCNS project source](https://github.com/janelia-flyem/male-cns) - Source for the project website and Dimorphism Explorer.
- [MaleCNS supplemental data](https://github.com/flyconnectome/2025malecns) - Derived data and analysis notebooks accompanying Berg et al., including sensorimotor flow and cell-type information.
- [FlyWire](https://flywire.ai/) - Adult female brain reconstruction, research resources, and links to exploration tools.
- [FlyWire annotations](https://github.com/flyconnectome/flywire_annotations) - Neuron annotations and other data products for the FlyWire v783 release.

Follow each upstream dataset's citation and licensing requirements. The license of this list does not relicense linked code, datasets, or artwork.

## Analysis libraries and viewers

- [Codex](https://github.com/murthylab/codex) by **Murthy Lab** - Source for the FlyWire Connectome Data Explorer. [Explore neurons](https://codex.flywire.ai/).
- [NAVis](https://github.com/navis-org/navis) by **navis-org** - Python tools for neuron morphology analysis, visualization, transformations, and data access.
- [fafbseg](https://github.com/navis-org/fafbseg-py) by **navis-org** - FlyWire/FAFB segmentation tools for meshes, skeletons, annotations, and connectivity queries, interoperable with NAVis.
- [malecns](https://github.com/natverse/malecns) by **natverse** - R access to MaleCNS data with metadata and morphology conveniences.
- [coconatfly](https://github.com/natverse/coconatfly) by **natverse** - Comparative connectomics across fly datasets, including FlyWire, hemibrain, MANC, FANC, and MaleCNS.
- [neuprint-python](https://github.com/connectome-neuprint/neuprint-python) by **connectome-neuprint** - Python client for querying connectivity and metadata through neuPrint.
- [CAVEclient](https://github.com/CAVEconnectome/CAVEclient) by **CAVEconnectome** - Python client for the Connectome Annotation Versioning Engine, used to access versioned connectomic data and annotations.
- [FlyWire network analysis](https://github.com/murthylab/flywire-network-analysis) by **Murthy Lab** - Research scripts and notebooks for network statistics, motifs, connectivity, and graph structure.

## Tutorials and papers

- [Fly connectome data tutorial](https://github.com/sjcabs/fly_connectome_data_tutorial) - Workshop materials for loading, analyzing, and visualizing major fly connectome datasets using Python and R.
- [FlyWire data access](https://github.com/seung-lab/FlyConnectome) - Seung Lab tutorials for programmatic access to FlyWire data, meshes, and annotations.
- [Neuronal wiring diagram of an adult brain](https://doi.org/10.1038/s41586-024-07558-y) - Dorkenwald et al., Nature (2024), the adult female brain connectome.
- [Whole-brain annotation and multi-connectome cell typing of Drosophila](https://doi.org/10.1038/s41586-024-07686-5) - Schlegel et al., Nature (2024), cell annotations and comparisons across connectomes.
- [Connectome-constrained networks predict neural activity across the fly visual system](https://www.nature.com/articles/s41586-024-07939-3) - Lappalainen et al., Nature (2024), the research behind flyvis.
- [Whole-body simulation of realistic fruit fly locomotion with deep reinforcement learning](https://www.nature.com/articles/s41586-025-09029-4) - The research accompanying flybody.

## Related lists

- [Awesome Fruit Fly Connectome](https://github.com/watthem/awesome-fruit-fly-connectome) - An earlier community list of datasets, tools, papers, and fly-connectome experiments.

## Contributing

Small projects are welcome. We prioritize a clear connection to fly connectomics, useful documentation, original creators, and accurate descriptions over star counts. Substantial ports belong here when their upstream origin is credited. Announcement-only projects must say that runnable code is pending.

Read [CONTRIBUTING.md](CONTRIBUTING.md), then submit a project or correct an existing entry. The list is maintained by [cobanov](https://github.com/cobanov), who also maintains PinFly.

## License

[CC0 1.0 Universal](LICENSE). Linked projects retain their own licenses.
