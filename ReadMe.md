The following table is a comparison of different underlying models used in different software's respective model-chains.  The goal of the table is to provide readers an easy reference guide to compare and contrast different photovoltaic performance modeling software.  The table also includes information about whether or not the implementation in the software matches the implementation in pvlib.

The table is open source and any user or software company can submit a pull request to include their information in this list.  If a free reference exists for the underlying model, the PDF is provided in a folder that matches the model category.  If no reference exists (especially for proprietary software algorithms) then the best known reference is provided in the "Other" markdown file instead.



| **Category** | **Model Name** | **PlantPredict** | **Uncertainty** | **PVLIB** | **PVSyst** | Uncertainty | **PVLIB** | **Comments** |
| ---------- | ------------- | ------------- | ------------ | ------ | -------- | ---- | ---- | ---- |
| Solar Position Algorithm | Solar Position Algorithm | NREL | 0.0003&deg; | &#9745; | Proprietary | "Some few arc-minutes" | &#9744; |  |
| Site Specific Models | Site Air Pressure for Altitude Correction of Inverters |  |  |  | None | N/A | &#9744; |  |
| Spectral | Relative Humidity from Dew Point | August-Roche-Magnus |  | &#9744; | None | N/A | &#9744; |  |
|  | Precipitable Water from Relative Humidity |  |  |  | ? |  |  |  |
|  | c-Si | First Solar v2.0 |  | &#9745; | Crest |  | &#9744; |  |
|  | a-Si | First Solar v2.0 |  | &#9745; | Sandia |  | &#9745; |  |
|  | Cd-Te | First Solar v2.0 |  | &#9745; | First Solar v2.0 |  | &#9745; |  |
| Transposition |  | Perez w/ coefficients |  | &#9745; | Perez w/out coefficients |  | &#9745; | Circumsolar as direct not in pvlib |
| Retro-Transposition |  | GTI-Dirint |  | &#9745 |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

# Acknowledgements



![[pvlib_logo.png]]
William F. Holmgren, Clifford W. Hansen, and Mark A. Mikofski. “pvlib python: a python package for modeling solar energy systems.” Journal of Open Source Software, 3(29), 884, (2018). [https://doi.org/10.21105/joss.00884](https://doi.org/10.21105/joss.00884)