
## PlantPredict
|  | **Model** | **Sources** | **Notes** |
| ---- | ---- | ---- | ---- |
| Dew_Point to Relative_Humidity | August-Roche-Magnus | See folder |  |
| Relative_Humidity to Precipitable_Water | Gueymard94 | See folder<br>https://pvlib-python.readthedocs.io/en/v0.4.2/generated/pvlib.atmosphere.gueymard94_pw.html#id5 | The accuracy of the model is stated as 20% for moderate predictable water and greater otherwise in the pvlib documentation. |
| Amorphous | First Solar Spectral 2.0 | https://pvlib-python.readthedocs.io/en/stable/reference/generated/pvlib.spectrum.spectral_factor_firstsolar.html?highlight=spectral_factor#pvlib.spectrum.spectral_factor_firstsolar |  |
| c-Si | First Solar Spectral 2.0 | https://pvlib-python.readthedocs.io/en/stable/reference/generated/pvlib.spectrum.spectral_factor_firstsolar.html?highlight=spectral_factor#pvlib.spectrum.spectral_factor_firstsolar |  |
| Cd-Te | First Solar Spectral 2.0 | https://pvlib-python.readthedocs.io/en/stable/reference/generated/pvlib.spectrum.spectral_factor_firstsolar.html?highlight=spectral_factor#pvlib.spectrum.spectral_factor_firstsolar |  |

## PVSyst


|  | **Model** | **Sources** | **Notes** |
| ---- | ---- | ---- | ---- |
| Dew_Point to Relative_Humidity | None | N/A |  |
| Relative_Humidity to Precipitable_Water | Gueymard94 | https://www.pvsyst.com/help/spectral-correction.htm | The accuracy of the model is stated as 20% for moderate predictable water and greater otherwise in the pvlib documentation. |
| Amorphous | Crest | https://www.pvsyst.com/help/amorphous_spectralcorr.htm |  |
| c-Si | Sandia | https://www.pvsyst.com/help/spectral-correction.htm |  |
| Cd-Te | First Solar Spectral 2.0 | https://www.pvsyst.com/help/spectral-correction.htm |  |

