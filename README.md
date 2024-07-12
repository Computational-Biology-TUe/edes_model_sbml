# The Eindhoven Diabetes Education Simulator (EDES) v1.0
SBML version of EDES v1.0

## Compatibility
The SBML model has been tested on the following platforms:
- [COPASI](http://copasi.org/) 
- [Julia](https://julialang.org/) with [SBMLImporter.jl](https://github.com/sebapersson/SBMLImporter.jl?tab=readme-ov-file) and [SBMLToolkit.jl](https://github.com/SciML/SBMLToolkit.jl)

## Julia Simulation

### Julia (SBMLToolkit)
```julia
using SBMLToolkit, ModelingToolkit, OrdinaryDiffEq

# Load the SBML model
odesys = structural_simplify(readSBML("EDES10_update_2.xml", ODESystemImporter()))

# Define the time span
tspan = (0.0, 240.0)

# Define the problem
prob = ODEProblem(odesys, [], tspan, [])

# Solve the problem
sol = solve(prob, Tsit5())
```

## Issues
Please raise an issue in this repository if you encounter any problems using this model.

