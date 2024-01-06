The following table is a comparison of different underlying models used in different software's respective model-chains.  The goal of the table is to provide readers an easy reference guide to compare and contrast different photovoltaic performance modeling software.  The table also includes information about whether or not the implementation in the software matches the implementation in pvlib.

The table is open source and any user or software company can submit a pull request to include their information in this list.  If a free reference exists for the underlying model, the PDF is provided in a folder that matches the model category.  If no reference exists (especially for proprietary software algorithms) then the best known reference is provided in the "Other" markdown file instead.


| Model |  | Software |  |  |  |  |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|  |  | **PlantPredict** |  |  | **PVSyst** |  |  | **Comments** |
| **Model Category** | **Model** | **Model** | **Uncertainty** | PVLIB | **Model** | Uncertainty | PVLIB |  |
| Solar Position Algorithm | Solar Position Algorithm | NREL | 0.0003&deg; | &#9745; | Proprietary | "Some few arc-minutes" | &#9744; |  |
| Site Specific Models | Site Air Pressure for Altitude Correction of Inverters |  |  |  | None | N/A | &#9744; |  |
| Spectral | Relative Humidity from Dew Point | August-Roche-Magnus |  | &#9744; | None | N/A | &#9744; |  |
|  | Precipitable Water from Relative Humidity |  |  |  | ? |  |  |  |
|  | Spectral Correction c-Si | First Solar v2.0 |  |  | Crest |  |  |  |
|  | Spectral Correction a-Si | First Solar v2.0 |  |  | Sandia |  |  |  |
|  | Spectral Correction Cd-Te | First Solar v2.0 |  |  | First Solar v2.0 |  |  |  |
| Transposition |  | Perez w/ coefficients  |  | &#9745; | Perez w/out coefficients |  | &#9745; | Implementation in software allow for allocation of circumsolar as direct which is not available in pvlib. |
| Retro-Transposition |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
