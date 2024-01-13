
The following table is a comparison of different underlying models used in different software's respective model-chains.  The goal of the table is to provide readers an easy reference guide to compare and contrast different photovoltaic performance modeling software.  The table also includes information about whether or not the implementation in the software matches the implementation in PVLlib.  

The table is open source and any user or software company can submit a pull request to include their information in this list.  If a free reference exists for the underlying model, the PDF is provided in a folder that matches the model category.  If no reference exists (especially for proprietary software algorithms) then the best known reference is provided in the "Other" markdown file instead.  Not every single model can be found in the table.  Some sub-models are omitted such as the calculation of delta T in the solar position algorithm in order to save space.  If the performance modeling software has multiple models for a given model type, only the most commonly used models are included.

Accuracy is presented in terms of mean bias difference (MBD), root mean squared difference (RMSD), standard deviation (SD), R squared (R2) or Uncertainty (U) depending on what is reported in the underlying paper.


|  |  | **PlantPredict** |  |  | **PVSyst** |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| **Category** | **Model_Type** | **Model** | **Published_Accuracy** | **PVLIB** | **Model** | **Published_Accuracy** | **PVLIB** |
| Solar_Position_Algorithm | Solar_Position_Algorithm | NREL | - U:  0.0003&deg; | &#9745; | Proprietary | - U:  0.08&deg; |  |
| Time Series | Minimum Time Step | 1 minute |  |  | 1 hour |  |  |
| Tracking | Astronomical Tracking | Marion & Dobos |  | &#9745; | Proprietary |  |  |
|  | Slope Aware Backtracking | Anderson & Mikofski |  | &#9745; | Proprietary |  |  |
|  | Terrain Aware Backtracking | None |  |  | None |  |  |
|  | Custom Backtracking | Yes |  |  | No |  |  |
|  | Diffuse Optimization | 3 Parameter |  |  | 1 Parameter |  |  |
|  | Wind Stow | None |  |  | Proprietary |  |  |
| Irradiance | Decomposition | Dirint | - MBD: -3 W/m<sup>2</sup><br>- RMSD: 74 W/m<sup>2</sup> | &#9745; | Erbs | - MBD:  -17 W/m<sup>2</sup><br>- RMSD: 88 W/m<sup>2</sup> | &#9745; |
|  | Transposition | Perez w/ coefficients | - MBD: -1%<br>- RMSD: 8% | &#9745; | Perez w/out coefficients | - MBD: -1%<br>- RMSD: 8% | &#9745; |
|  | Retro-Transposition | GTI-Dirint | - MBD: 0.0 W/m<sup>2</sup><br>- RMSD: 6.4 W/m<sup>2</sup> | &#9745; | Reverse Hay | - MBD: Unknown<br>- RMSD: Unknown |  |
| Optical | IAM | Physical |  | &#9745; | Fresnel |  |  |
|  | Soiling | Time-Step Level |  |  | Monthly |  |  |
|  | Horizon Shading (Far Shading) | Sub-TimeStep |  |  |  |  |  |
|  | Near Shading | Polygon Clipping |  |  | Polygon Clipping |  |  |
|  | Bifacial | NREL BifacialVF |  |  | Proprietary |  |  |
| Spectral | Relative_Humidity from Dew_Point | August-Roche-Magnus |  |  | None | N/A |  |
|  | Precipitable_Water from Relative_Humidity | No Name |  |  | No Name |  |  |
|  | c-Si | First Solar v2.0 |  | &#9745; | Crest |  |  |
|  | a-Si | First Solar v2.0 |  | &#9745; | Sandia |  | &#9745; |
|  | Cd-Te | First Solar v2.0 |  | &#9745; | First Solar v2.0 |  | &#9745; |
| DC | Cell Thermal Model | Modified Faiman |  |  | Modified Faiman |  |  |
|  | Diode Model | Single Diode |  |  | Single Diode |  |  |
|  | Mismatch | Simple Statistical |  |  | Detailed |  |  |
|  | Wiring | % at STC |  |  | Ohmic |  |  |
|  | Degradation | % |  |  | % |  |  |
| AC | Inverter Off MPP | Proprietary |  |  | Proprietary |  |  |
|  | Inverter Efficiency | Sandia |  | &#9745; | Quadratic Interpolation |  |  |
|  | Air Pressure for Altitude Correction of Inverters | Yes |  |  | No |  | &#9744; |
|  | Transformer | McCann Lawrence |  |  | Proprietary |  |  |
|  | Wiring | % at STC |  |  | Ohmic |  |  |

# Acknowledgements



![[pvlib_logo.png]]
William F. Holmgren, Clifford W. Hansen, and Mark A. Mikofski. “pvlib python: a python package for modeling solar energy systems.” Journal of Open Source Software, 3(29), 884, (2018). [https://doi.org/10.21105/joss.00884](https://doi.org/10.21105/joss.00884)