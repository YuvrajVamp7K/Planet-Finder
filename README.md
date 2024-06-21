# PlanetFinder: A Lightkurve Project for Exoplanet Detection

PlanetFinder is a Python-based project designed to detect exoplanets using light curve data from the TESS mission. By leveraging the Lightkurve library, PlanetFinder provides tools to search for, analyze, and visualize potential exoplanet transits.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Finding Target IDs](#finding-target-ids)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Introduction

PlanetFinder is aimed at citizen scientists and astronomers who want to participate in the exciting field of exoplanet discovery. Using data from the TESS mission, this project allows users to identify and analyze potential exoplanet transits through an easy-to-use Python interface.

## Features

- Search and download light curve data from TESS
- Detect potential exoplanet transits using Box Least Squares (BLS) periodograms
- Visualize light curves and transit events
- Filter and clean light curve data
- Phase-fold light curves to inspect periodic signals

## Installation

To get started with PlanetFinder, follow these steps:

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/planetfinder.git
    cd planetfinder
    ```

2. **Create and activate a virtual environment:**
    ```bash
    python -m venv env
    source env/bin/activate  # On Windows use `env\Scripts\activate`
    ```

3. **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## Finding Target IDs

To analyze light curve data for specific stars, you need the Target Identifier (TIC ID) for stars observed by the TESS mission. Here's how you can find them:

1. **TESS Input Catalog (TIC):**
   - The TIC ID is a unique identifier for stars in the TESS Input Catalog.
   - You can search for TIC IDs using the [MAST Portal](https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html) or the [ExoFOP-TESS](https://exofop.ipac.caltech.edu/tess/) website.

2. **Using the MAST Portal:**
   - Go to the [MAST Portal](https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html).
   - Enter the name or coordinates of the star you are interested in.
   - The search results will provide the TIC ID among other details.

3. **Using ExoFOP-TESS:**
   - Visit the [ExoFOP-TESS](https://exofop.ipac.caltech.edu/tess/) website.
   - You can search by object name or TIC ID.
   - This site also provides additional information and resources for the stars observed by TESS.

4. **Example:**
   - If you are interested in the star "Alpha Centauri," you would search for it on the MAST Portal or ExoFOP-TESS.
   - Once you locate the star, note the TIC ID (e.g., TIC 12345678).

5. **Finding Data in Lightkurve:**
   - Once you have the TIC ID, you can use it to search for light curve data in Lightkurve:
     ```python
     from lightkurve import search_lightcurvefile
     search_result = search_lightcurvefile("TIC 12345678", mission='TESS')
     lc_file = search_result.download()
     lc = lc_file.PDCSAP_FLUX.remove_nans()
     ```

## Contributing

We welcome contributions from the community! To contribute to PlanetFinder:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes and push to your branch.
4. Open a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

PlanetFinder uses the following open-source libraries and resources:

- [Lightkurve](https://github.com/lightkurve/lightkurve)
- [TESS Mission](https://tess.mit.edu/)
- [Matplotlib](https://matplotlib.org/)
- [NumPy](https://numpy.org/)

We would also like to thank the community of citizen scientists and professional astronomers who contribute to the field of exoplanet discovery.

---
