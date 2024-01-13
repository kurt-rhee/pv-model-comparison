

## Goals
The following table is a comparison of the underlying models used in different software's respective model-chains.  The goal of the table is to provide readers an easy reference guide to compare and contrast different photovoltaic performance modeling software.  The table also includes information about whether or not the implementation in the software matches the implementation in PVLlib.  Not every single model can be found in the table.  Some sub-models are omitted such as the calculation of delta T in the solar position algorithm in order to save space. If the performance modeling software has multiple models for a given model type, only the most commonly used models are included.

## Column Descriptions
- **Category**:  A grouping of models that relate to a specific folder in the repository structure
- **Model_Type**:  The type of model being described in the table
- **Model**:  The name of the model used by a given performance modeling software
- **Metric**:  Accuracy is presented in terms of the following metrics depending on what is stated in the cited paper:
	- mean bias difference (MBD),
	- root mean squared difference (RMSD),
	- maximum difference (MxD),
	- standard deviation (SD),
	- R squared (R2)
	- Uncertainty (U)
	- Model is precise (-)
- **Accuracy**:  
	- If an accuracy value is present in the table, then the accompanying publication is included in the repository folder structure.  
	- Published accuracy must be from a third party and reputably published in order to be included in this table.  
	- If many different published accuracy values exist such as accuracy values at different time-steps, then only the most relevant values are included in the table.
	- Discerning readers may refer to the reference for additional information.
- **PVLIB**:  The model implemented in the software is identical or very nearly identical to the implementation in pvlib.

## Contributing
The table is open source and any user or software company can submit a pull request to include their information in this list.  

- Rules for contribution:
	- If a free reference exists for the underlying model, please include the PDF in a folder that matches the model category.
	- If no reference exists (especially for proprietary software algorithms) then the best known reference is provided in the "_Notes_" markdown file instead.   




|  |  | **PlantPredict** |  |  |  | **PVSyst** |  |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| **Category** | **Model_Type** | **Model** | **Metric** | **Accuracy** | **PVLIB** | **Model** | **Metric** | **Accuracy** | **PVLIB** |
| Solar_Position_Algorithm | Solar_Position_Algorithm | NREL | U | 0.0003&deg; | &#9745; | Proprietary | U | 0.08&deg; |  |
| Time Series | Minimum Time Step | 1 minute | MxD | ~< 0.4% |  | 1 hour | MxD | ~< 1.8% |  |
| Tracking | Astronomical Tracking | Marion & Dobos | - | - | &#9745; | Proprietary | - | - |  |
|  | Slope Aware Backtracking | Anderson & Mikofski | - | - | &#9745; | Proprietary | - | - |  |
|  | Terrain Aware Backtracking | None |  |  |  | None |  |  |  |
|  | Custom Backtracking | Yes | - | - |  | No | - | - |  |
|  | Diffuse Optimization | 3 Parameter |  |  |  | 1 Parameter |  |  |  |
|  | Wind Stow | None |  |  |  | Fixed Threshold |  |  |  |
| Irradiance | Decomposition | Dirint | MBD<br>RMSD | -3 W/m<sup>2</sup><br>74 W/m<sup>2</sup> | &#9745; | Erbs | MBD<br>RMSD | -17 W/m<sup>2</sup><br>88 W/m<sup>2</sup> | &#9745; |
|  | Transposition | Perez w/ coefficients | MBD<br>RMSD | -1%<br>8% | &#9745; | Perez w/out coefficients | MBD<br>RMSD | -1%<br>8% | &#9745; |
|  | Retro-Transposition | GTI-Dirint | MBD<br>RMSD | 0.0 W/m<sup>2</sup><br>6.4 W/m<sup>2</sup> | &#9745; | Reverse Hay | MBD<br>RMSD | Unknown<br>Unknown |  |
| Optical | IAM | Physical |  |  | &#9745; | Fresnel |  |  |  |
|  | Soiling | Time-Step Level |  |  |  | Monthly |  |  |  |
|  | Horizon Shading (Far Shading) | Sub-TimeStep |  |  |  | 1 hour |  |  |  |
|  | 3D Near Shading | Polygon Clipping | - | - |  | Polygon Clipping | - | - |  |
|  | Bifacial | NREL BifacialVF |  |  | &#9745; | Proprietary |  |  |  |
| Spectral | Relative_Humidity from Dew_Point | August-Roche-Magnus |  |  |  | None |  | N/A |  |
|  | Precipitable_Water from Relative_Humidity | Gueymard94 |  |  | &#9745; | Gueymard94 |  |  | &#9745; |
|  | c-Si | First Solar v2.0 |  |  | &#9745; | Crest |  |  |  |
|  | a-Si | First Solar v2.0 |  |  | &#9745; | Sandia |  |  | &#9745; |
|  | Cd-Te | First Solar v2.0 |  |  | &#9745; | First Solar v2.0 |  |  | &#9745; |
| DC | Cell Thermal Model | Modified Faiman |  |  |  | Modified Faiman |  |  |  |
|  | Diode Model | Single Diode |  |  |  | Single Diode |  |  |  |
|  | Mismatch | Simple Statistical |  |  |  | Detailed |  |  |  |
|  | Wiring | % at STC |  |  |  | Ohmic |  |  |  |
|  | Degradation | % |  |  |  | % |  |  |  |
| AC | Inverter Off MPP | Proprietary |  |  |  | Proprietary |  |  |  |
|  | Inverter Efficiency | Sandia |  |  | &#9745; | Quadratic Interpolation |  |  |  |
|  | Air Pressure for Altitude Correction of Inverters | Yes |  |  |  | No |  |  | &#9744; |
|  | Transformer | McCann Lawrence |  |  |  | Proprietary |  |  |  |
|  | Wiring | % at STC |  |  |  | Ohmic |  |  |  |

# Contributions
- Kurt Rhee
- Renn Darawali

# References

![[pvlib_logo.png]]
William F. Holmgren, Clifford W. Hansen, and Mark A. Mikofski. “pvlib python: a python package for modeling solar energy systems.” Journal of Open Source Software, 3(29), 884, (2018). [https://doi.org/10.21105/joss.00884](https://doi.org/10.21105/joss.00884)