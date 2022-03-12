## About

This repo contains three Calliope energy system models:
- [Bangalore](https://www.sciencedirect.com/science/article/pii/S0306261921000313), city-district scale model set in Bangalore, India.  
- [UK](https://www.sciencedirect.com/science/article/pii/S0306261917302775), modelling the energy grid between zones of the UK.  
- [Europe](https://www.sciencedirect.com/science/article/pii/S2542435120303366), a model of the European electricity system at national scale.

The models in this repo are specific version of existing Calliope models, allowing specific alterations used for benchmarking Calliope.
The original models can be found here.
- Bangalore: https://github.com/brynpickering/bangalore-calliope
- UK: https://github.com/calliope-project/uk-calliope
- Europe: https://github.com/calliope-project/euro-calliope

The Calliope fork benchmarked with these models can be found [here](https://github.com/brmanuel/calliope).

To run a model, you need to install the Calliope pip package from the above fork and then run 

```
python calliope run path/to/model.yaml --scenario=overrides
```

Where <overrides> is a comma-separated list of model-specific overrides specified in the respective overrides.yaml file of each model.
