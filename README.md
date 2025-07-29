# Neutron Survival Simulation using Russian Roulette Method

This repository contains a simple Monte Carlo simulation of neutron behavior using the Russian Roulette method. The simulation estimates how many neutrons survive after undergoing scattering or absorption, based on their energy levels.

## Overview

In nuclear physics simulations, especially neutron transport, the **Russian Roulette** technique is often used to probabilistically terminate or continue the paths of particles based on their likelihood of survival or contribution to the system. This simulation models the fate of neutrons given random initial energies and a basic survival probability function.

## Features

- Simulates neutron interactions using stochastic methods
- Models energy loss due to scattering or collision
- Applies the Russian Roulette method to terminate low-contribution neutrons
- Outputs the number of surviving neutrons

## How It Works

1. **Neutron Initialization**: Each neutron is assigned a random energy between 0.1 MeV and 2.0 MeV.
2. **Threshold Check**: Neutrons with energy below a defined threshold (`ENERGY_THRESHOLD = 0.7`) are immediately terminated.
3. **Scattering Event**: Remaining neutrons lose some energy to simulate scattering.
4. **Russian Roulette Termination**:
   - High-energy neutrons (`> 1.0 MeV`) have a **5% survival** probability.
   - Low-energy neutrons (`≤ 1.0 MeV`) have a **10% survival** probability.
5. **Survivors Count**: The simulation counts neutrons that survive both threshold checks and Russian Roulette.

## Parameters

You can modify the following constants in the script to experiment with the simulation:

```python
NUM_NEUTRONS = 10000             # Total neutrons to simulate
ENERGY_THRESHOLD = 0.7           # Minimum energy to be considered for survival
MAX_ENERGY = 2.0                 # Maximum initial energy
SCATTERING_THRESHOLD = 1.0       # Energy boundary for different survival probabilities



