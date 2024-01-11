
The following table is a comparison of different underlying models used in different software's respective model-chains.  The goal of the table is to provide readers an easy reference guide to compare and contrast different photovoltaic performance modeling software.  The table also includes information about whether or not the implementation in the software matches the implementation in PVLlib.  

The table is open source and any user or software company can submit a pull request to include their information in this list.  If a free reference exists for the underlying model, the PDF is provided in a folder that matches the model category.  If no reference exists (especially for proprietary software algorithms) then the best known reference is provided in the "Other" markdown file instead.  Not every single model can be found in the table.  Some sub-models are omitted such as the calculation of delta T in the solar position algorithm in order to save space.  If the performance modeling software has multiple models for a given model type, only the most commonly used models are included.

Accuracy is presented in terms of mean bias difference (MBD), root mean squared difference (RMSD), standard deviation (SD), R squared (R2) or Uncertainty (U) depending on what is reported in the underlying paper.


|  |  | **PlantPredict** |  |  | **PVSyst** |  |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| **Category** | **Model_Type** | **Model** | **Published_Accuracy** | **PVLIB** | **Model** | **Published_Accuracy** | **PVLIB** | **Comments** |
| Solar_Position_Algorithm | Solar_Position_Algorithm | NREL | - U:  0.0003&deg; | &#9745; | Proprietary | - U:  0.08&deg; | &#9744; | None |
| Time Series | Minimum Time Step | 1 minute |  |  | 1 hour |  |  | None |
| Tracking | Astronomical Tracking | Marion & Dobos |  | &#9745; | 2D Flat |  |  | None |
|  | Slope Aware Backtracking | Anderson & Mikofski |  | &#9745; | None |  |  | None |
|  | Terrain Aware Backtracking | None |  |  | None |  |  | Terrain Backtracking not in pvlib |
|  | Diffuse Optimization | 3 Parameter |  |  | 1 Parameter |  |  | Diffuse Optimization not in pvlib |
|  | Wind Stow | None |  |  | Proprietary |  |  | Wind Stow not in pvlib |
| Irradiance | Decomposition | Dirint | - MBD: -3 W/m<sup>2</sup><br>- RMSD: 74<br>- SD:  74 | &#9745; | Erbs | - MBD:  -17<br>- RMSD: 88<br>- SD: 87 | &#9745; | Error reported at hourly interval |
|  | Transposition | Perez w/ coefficients |  | &#9745; | Perez w/out coefficients |  | &#9745; | Circumsolar as direct not in pvlib |
|  | Retro-Transposition | GTI-Dirint (Reverse Perez) |  | &#9745; | Reverse Hay |  |  |  |
| Optical | IAM | Physical |  | &#9745; | Fresnel |  | &#9744; |  |
|  | Soiling | Time-Step Level |  |  | Monthly |  |  |  |
|  | Horizon Shading (Far Shading) | Sub-TimeStep |  | &#9744; |  |  |  |  |
|  | Near Shading | Polygon Clipping |  |  | Polygon Clipping |  |  |  |
|  | Bifacial |  |  |  |  |  |  |  |
| Spectral | Relative_Humidity from Dew_Point | August-Roche-Magnus |  | &#9744; | None | N/A | &#9744; |  |
|  | Precipitable_Water from Relative_Humidity |  |  |  |  |  | &#9744; |  |
|  | c-Si | First Solar v2.0 |  | &#9745; | Crest |  | &#9744; |  |
|  | a-Si | First Solar v2.0 |  | &#9745; | Sandia |  | &#9745; |  |
|  | Cd-Te | First Solar v2.0 |  | &#9745; | First Solar v2.0 |  | &#9745; |  |
| DC | Cell Thermal Model | Modified Faiman |  |  | Modified Faiman |  |  |  |
|  | Irradiance Level |  |  |  |  |  |  |  |
|  | Diode Model | Single Diode |  |  | Single Diode |  |  |  |
|  | Mismatch |  |  |  |  |  |  |  |
|  | Wiring | % at STC |  |  | Ohmic |  |  |  |
|  | Degradation | % |  |  | % |  |  |  |
| AC | Inverter Off MPP | Proprietary |  | &#9744; | Proprietary |  |  | None |
|  | Inverter Efficiency | Sandia |  | &#9745; |  |  |  |  |
|  | Air Pressure for Altitude Correction of Inverters |  |  |  | None |  | &#9744; |  |
|  | Transformer |  |  |  |  |  |  |  |
|  | Wiring | % at STC |  |  | Ohmic |  |  | None |

# Acknowledgements



![[pvlib_logo.png]]
William F. Holmgren, Clifford W. Hansen, and Mark A. Mikofski. “pvlib python: a python package for modeling solar energy systems.” Journal of Open Source Software, 3(29), 884, (2018). [https://doi.org/10.21105/joss.00884](https://doi.org/10.21105/joss.00884)