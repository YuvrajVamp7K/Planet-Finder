PlanetFinder: A Lightkurve Project for Exoplanet Detection
PlanetFinder is a Python-based project designed to detect exoplanets using light curve data from the TESS mission. By leveraging the Lightkurve library, PlanetFinder provides tools to search for, analyze, and visualize potential exoplanet transits.

Table of Contents
Introduction
Features
Installation
Finding Target IDs
Contributing
License
Acknowledgements
Introduction
PlanetFinder is aimed at citizen scientists and astronomers who want to participate in the exciting field of exoplanet discovery. Using data from the TESS mission, this project allows users to identify and analyze potential exoplanet transits through an easy-to-use Python interface.

Features
Search and download light curve data from TESS
Detect potential exoplanet transits using Box Least Squares (BLS) periodograms
Visualize light curves and transit events
Filter and clean light curve data
Phase-fold light curves to inspect periodic signals
Installation
To get started with PlanetFinder, follow these steps:

Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/planetfinder.git
cd planetfinder
Create and activate a virtual environment:

bash
Copy code
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Finding Target IDs
To analyze light curve data for specific stars, you need the Target Identifier (TIC ID) for stars observed by the TESS mission. Here's how you can find them:

TESS Input Catalog (TIC):

The TIC ID is a unique identifier for stars in the TESS Input Catalog.
You can search for TIC IDs using the MAST Portal or the ExoFOP-TESS website.
Using the MAST Portal:

Go to the MAST Portal.
Enter the name or coordinates of the star you are interested in.
The search results will provide the TIC ID among other details.
Using ExoFOP-TESS:

Visit the ExoFOP-TESS website.
You can search by object name or TIC ID.
This site also provides additional information and resources for the stars observed by TESS.
Example:

If you are interested in the star "Alpha Centauri," you would search for it on the MAST Portal or ExoFOP-TESS.
Once you locate the star, note the TIC ID (e.g., TIC 12345678).
Finding Data in Lightkurve:

Once you have the TIC ID, you can use it to search for light curve data in Lightkurve:
python
Copy code
from lightkurve import search_lightcurvefile
search_result = search_lightcurvefile("TIC 12345678", mission='TESS')
lc_file = search_result.download()
lc = lc_file.PDCSAP_FLUX.remove_nans()
Contributing
We welcome contributions from the community! To contribute to PlanetFinder:

Fork the repository.
Create a new branch for your feature or bugfix.
Commit your changes and push to your branch.
Open a pull request with a detailed description of your changes.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgements
PlanetFinder uses the following open-source libraries and resources:

Lightkurve
TESS Mission
Matplotlib
NumPy
We would also like to thank the community of citizen scientists and professional astronomers who contribute to the field of exoplanet discovery.

