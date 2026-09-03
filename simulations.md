# Simulations

Below is a detailed description of the requested configuration of all simulations as extracted from the protocol paper. The purpose of this page is to have everything available in one page, and enriched with answers from potential questions as each model is being set up. Modelers are requested to explicitly document what they have done in the [models page](models.md), even if this repeats information from here. When Earth is mentioned, it means conditions as close as possible to preindustrial, defined as the year 1850. The duration of the spinup will be model-dependent and should be documented, and the equilibrated simulation(s) should be 150 years, unless the 4xCO2 simulation comes to a complete equilibrium earlier. 

## Benchmark (CREME_BM)

This is the entry ticket to CREME, and need to be performed by all models. 

* Ocean: Dynamic. If not possible, a Q-flux ocean is also acceptable as long as the heat fluxes are those of Earth. Fixed sea surface temperatures are also acceptable if no ocean calculations of any kind are possible.
* Bathymetry: Earth if dynamic ocean, or whatever the Q-flux ocean configuration uses.
* Sea ice: Dynamic, or thermodynamic if sea ice flow is not possible across grid cells. Prescribed to Earth values if no prognostic calculations are possible.
* Topography: Earth.
* Vegetation: None.
* Land ice: No prescribed glaciers; snow accumulation imitates the cryosphere. The topography of land should resemble that of the top of the Earth's glaciers, so in places with thick glaciers like in Greenland and Antarctica the model surface is where the top of glaciers is.
* Atmosphere: 78.1 % N<sub>2</sub>, 20.9 % O<sub>2</sub>, 0.9 % Ar (if possible; make it N<sub>2</sub> if not).
* Long-lived GHGs: Earth CO<sub>2</sub> (284 ppmv). CH<sub>4</sub>, N<sub>2</sub>O, CFCs set to zero.
* Water vapor: prognostic.
* Ozone and aerosols: Earth.

## Preindustrial (CREME_PI)

Only models that can meet these requirements should perform this. The configuration is the same as in benchmark, with the following changes:

* Vegetation: Earth.
* Land ice: Earth.
* Long-lived GHGs: Earth; CO<sub>2</sub> as in benchmark (284 ppmv), CH<sub>4</sub> 808 ppbv, N<sub>2</sub>O 273 ppbv, CFCs as in benchmark (zero).
* Water vapor: as in benchmark.

## 4xCO<sub>2</sub> (CREME_4xCO2)

Mandatory simulation for all models. The configuration is the same as in benchmark, with only one change: the CO<sub>2</sub> concentration is 4x that of the benchmark (to 1136 ppmv), and the simulation should be an exact continuation of the model state at the end of the spinup. 

# Simulation names

The table below describes the simulation names models should use for their experiments. The model description pages should use the names below when describing which simulations have been performed. 

## Mandatory simulations

All models should perform these. CREME_PI is mandatory only for the models that can perform it without additional model development. 

| Simulation name | Description |
| --- | --- |
| CREME_BK | Benchmark simulation described above. Mandatory. |
| CREME_PI | Preindustrial simulation described above. Mandatory if it can be performed. Given the names below, this is equivalent to CREME_BKwVEGwLANDICEwGHGs. |
| CREME_4xCO2 | 4xCO<sub>2</sub> simulation described above. Mandatory. |

## Optional in-between simulations

Models should perform any of these that they can. 

| Simulation name | Description |
| --- | --- |
| CREME_BKwVEG | Same as CREME_BK, with Earth's vegetation. |
| CREME_BKwLANDICE | Same as CREME_BK, with land ice instead of just snow. |
| CREME_BKwGHGs | Same as CREME_BK, with CH<sub>4</sub> 808 ppbv and N<sub>2</sub>O 273 ppbv. |
| | |
| CREME_BKwVEGwLANDICE | Same as CREME_BK, with Earth's vegetation and land ice instead of just snow. |
| CREME_BKwVEGwGHGs | Same as CREME_BK, with Earth's vegetation and CH<sub>4</sub> 808 ppbv and N<sub>2</sub>O 273 ppbv. |
| CREME_BKwLANDICEwGHGs | Same as CREME_BK, with land ice and CH<sub>4</sub> 808 ppbv and N<sub>2</sub>O 273 ppbv. |
| | |
| CREME_BKwQflux | Same as CREME_BK with a Q-flux ocean using Earth's heat fluxes. This is only applicable for models that used a dynamic ocean in their CREME_BK simulation. |

## Optional basic simulations

These simulations have low priority. 

| Simulation name | Description |
| --- | --- |
| CREME_BKzeroQflux | Same as CREME_BK with a zero Q-flux ocean. |
| CREME_woSEAICE | Same as CREME_BK without sea ice. |
| CREME_woTOPO | Same as CREME_BK with flat topography. |
| CREME_woSNOW | Same as CREME_BK without snow. |
| CREME_woGHGs | Same as CREME_BK with zero CO<sub>2</sub>. |
| CREME_wOTHERSTAR | Same as CREME_BK with a different star (document which and include it in the run name). |
| CREME_wOTHERORBIT | Same as CREME_BK with a different orbit (document which and include it in the run name). |
