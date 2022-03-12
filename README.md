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

Where overrides is a comma-separated list of model-specific overrides specified in the respective overrides.yaml file of each model.

## Overrides

### Europe Model

The baseline model is specified using override "diw_assumptions,ose_capacity,diw_battery_baseline_cost,jrc_etri_2014_renewable_costs,equal_interest_rate,no_hydrogen"

Six model variations were benchmarked:
   
1) diw_battery_baseline_cost,topology,no_hydro_reservoir,no_csv,no_co2_caps,no_renewable_shares,
2) diw_battery_baseline_cost,topology,topology_with_grp_constr,
3) diw_battery_baseline_cost,germany_only,
4) diw_battery_low_cost,germany_only,
5) diw_battery_lowest_cost,germany_only,
6) diw_battery_baseline_cost,germany_only,no_co2_caps,


### UK Model

The baseline model is specified using override "base".

Six model variations were benchmarked:

1) base 
2) no_imports,cost_batt_high,r80, 
3) double_imports,new_nuclear,cost_batt_breakthrough,r40, 
4) cost_batt_low,r50, 
5) cost_batt_breakthrough,no_imports,r90, 
6) cost_batt_breakthrough,no_imports,r100


### Bangalore Model

The baseline model has no overrides.

Two model variations were benchmarked:

1) cost_of_carbon_high_myfix
2) cost_of_carbon_low_myfix


### Benchmarking related overrides

For benchmarking, a separate set of overrides allows controling various aspects of the solving process:

- subsettime_Xd: runs the model over a period of X days, starting at January 1
- solver_X_Y: selects the solver (Gurobi vs. CBC) and the solving algorithm (primal simplex, dual simplex, barrier, barrier with crossover)
- unscaled/autoscaled: chooses whether automatic input scaling should be applied or not.
