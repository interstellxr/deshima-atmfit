# deshima-atmfit
Python package for fitting an atmospheric transmission model to a DESHIMA spectrum to derive the PWV.

## Overview
deshima-atmfit is a Python package which adjusts and atmospheric transmission model to an atmospheric spectrum obtained with DESHIMA to calculate the PWV. The model used in this package is the ATM model (Pardo et al. 2001). This package enables an in-situ estimation of the PWV. 

An online Jupyter notebook is available (a Google account is necessary) :

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UzD4JTTfT0zpwREfByMLgebAKUaQqXdi#scrollTo=8BTtHOikDAqB)

## Installation and requirements
The package has several dependencies :
- `xarray`
- `astropy`
- `numpy`
- `scipy`
- `pandas`

## Usage
Function : ATM_fit

Purpose : Fits an atmospheric transmission model to spectral data to derive PWV values and atmospheric temperature.

Parameters :

    da (xarray.DataArray): The input spectral data.
    ddb (fits.HDUList): The .fits file containing filter response functions.
    pwv0 (float, optional): Initial PWV value. Default is 1.0 mm.
    dt (int, optional): Time step for processing. Default is 1.
    *ranges_weights (tuples of floats): Frequency ranges and their corresponding weights in the form (fmin, fmax, weight). Default is the whole range with no weights.

Returns :

    new_da (xarray.DataArray): A DataArray with fitted brightness temperatures and derived parameters:
    PWV: Precipitable Water Vapor.
    T_atm: Atmospheric temperature.
    PWV_std: Standard deviation of PWV.
    T_atm_std: Standard deviation of atmospheric temperature.
