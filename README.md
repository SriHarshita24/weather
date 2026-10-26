# Weather Simulation Using Python

A Python-based weather simulation that models changing weather conditions using probabilistic state transitions and state-specific holding times.

The project uses NumPy to simulate weather states, generate sequences of weather conditions, and estimate the percentage of time spent in each state.

## Overview

This project implements a `WeatherSimulation` class that represents weather conditions as states: sunny, cloudy, rainy, and snowy.

Each state has a set of transition probabilities that determine the next weather state when its holding time expires. The simulation can generate weather sequences over a specified number of hours and calculate the percentage distribution of weather conditions.

The project also includes test functions to validate transition probabilities, holding times, exception handling, and simulated state distributions.

## Features

- Simulates four weather states: sunny, cloudy, rainy, and snowy
- Models transitions between weather states using probability distributions
- Supports state-specific holding times
- Tracks the current weather state and remaining holding time
- Generates an iterable sequence of weather states
- Simulates weather conditions over a specified number of hours
- Calculates the percentage of time spent in each weather state
- Validates transition probabilities
- Tests state transitions, holding times, and simulation results

## Tech Stack

- **Python** — simulation logic and implementation
- **NumPy** — random state selection and numerical calculations
- **Collections.OrderedDict** — maintains an ordered representation of transition probabilities and holding times

## How It Works

1. **Configure the model:** Define transition probabilities for each weather state.
2. **Set holding times:** Specify how long each state lasts before a transition occurs.
3. **Initialize the simulation:** Start with the sunny state.
4. **Advance the simulation:** Decrease the remaining holding time and select the next state when the holding time expires.
5. **Generate weather sequences:** Iterate through weather states for a specified number of hours.
6. **Calculate state distribution:** Count occurrences of each state and calculate its percentage of the total simulation period.
7. **Validate the model:** Run tests for probability totals, holding times, and expected simulation distributions.

## Example Configuration

The simulation uses the following transition probabilities:

| Current state | Sunny | Cloudy | Rainy | Snowy |
|---|---:|---:|---:|---:|
| Sunny | 0.70 | 0.30 | 0.00 | 0.00 |
| Cloudy | 0.50 | 0.30 | 0.15 | 0.05 |
| Rainy | 0.60 | 0.20 | 0.15 | 0.05 |
| Snowy | 0.70 | 0.10 | 0.05 | 0.15 |

The configured holding times are:

- Sunny: 1 time step
- Cloudy: 2 time steps
- Rainy: 2 time steps
- Snowy: 1 time step

These values are model assumptions used by the simulation, not real-world weather forecasts.

## Getting Started

### Prerequisites

- Python 3
- NumPy

### Installation

Clone the repository:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_DIRECTORY>
```

Install the required dependency:

```bash
python -m pip install numpy
```

### Run the Simulation Tests

Save the Python code in the appropriate `.py` file, then run:

```bash
python your_file.py
```

The script reads an integer from standard input before executing the test suite. Provide the input expected by your original assignment or test environment.

The program prints `1` when the final test conditions pass and `0` when they fail.

## Testing

The included test functions check:

- Whether transition probabilities sum to 1
- Whether invalid transition probabilities raise a `RuntimeError`
- Whether weather states respect their configured holding times
- Whether the simulation produces state percentages within the configured tolerances
- Whether the weather-state iterator produces successive states

## Limitations

- The simulation uses predefined transition probabilities and holding times.
- It does not use live weather observations or meteorological data.
- Its output represents a probabilistic simulation rather than a real weather forecast.
- Results depend on the configured parameters and random state selection.

## Future Improvements

- Allow users to configure transition probabilities and holding times.
- Add visualizations of weather-state distributions over time.
- Support reproducible experiments through configurable random seeds.
- Add unit tests using a dedicated testing framework.
- Compare simulated state distributions under different parameter configurations.

## Disclaimer

This project is intended for educational purposes to demonstrate probabilistic state transitions, simulation, and numerical analysis in Python. It is not intended for real-world weather forecasting.
