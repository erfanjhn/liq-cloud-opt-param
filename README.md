# liq_cloud_opt_param
This repository allows the verification of the fits used to derive the parameterizations included in the paper: "Uncertainty of SW cloud radiative effect in atmospheric models due to the parameterization of liquid cloud optical properties" (E.Jahangir et al.) submitted to JAMES journal.

## Ref_Log.nc 
The reference Single Scattering Properties (SSPs) calculated with the Lorenz-Mie method for 4 shapes of Lognormal distribution function and with 9 spectral averaging methods on 80 effective radii ranging between 1 and 50 micro meters and tabulated in netCDF file called in this netCDF file.

#### The variables of this netCDF file encompasses the SSPs:
Qext, g and Single scattering albedo(SSA) derived for each of 9 spectral methods explained in section 3.2 of the article.

#### Each of variables are defined by 3 attributes:
effective radius (r_eff) with dimension of 80,Logarithmic function DSD shape (presented by "sigma") with dimension of 4
and RRTMG bands (denoted by "band") having a deminesion of 14 (in the shortwave).

## T1, T10, T20, R1, R10, R20, Thick and Thin
These folders correspond to the spectral averaging methods explained in the section 3.2 of the article. Each of them contains 4 sub-folders  called:
### SigmaXX
XX representing the 4 shapes of Log distribution function.   
The netCDF files called #### comprise the coefficients of the fits explained in the section 3.3 of the paper. In order to visualise the fits of SSPs, the user must apply the coeficinets from this netCDF file in the Eqs. 20-22 of the paper as follows:\
1-Read the file with a desired netCDF reader and use 'coeff_sw' variable.
If we call the netCDF file, "data", the coefficients required to interpret the SSPs in a selected 'band' are:

##### for Qext :
p_ext2=data['coeff_sw'][band,16:22]        
p_ext1=data['coeff_sw'][band,0:6] 

##### for g:
p_g2=data['coeff_sw'][band,27:32]  
p_g1=data['coeff_sw'][band,11:16]

The cut-points for g and Qext are

##### for SSA:

p_SSA2=data['coeff_sw'][band,22:27] \
p_SSA1=data['coeff_sw'][band, 6:11]



2-As explained in section 3.3 of the paper the fits are performed on two parts of reference values. 
"1" and "2" suffixes for each of SSPs (p_XX1, p_XX2) indicate the corresponding coefficients to the first and second part of fits respectively.That means for the r_eff range lower(greater) than the cut_point the coefficients having "1"("2") in suffix must be used.


The cut-points for g and Qext are defined for each of 14 band as:\
(3.45,2.78,2.325,2.045,1.78,1.45,1.26,1.01,0.7,0.533,0.39,0.3,0.23,3.92)*2

And for the SSA it is:
r_cut=data['coeff_sw'][band,32]


Note that the band arrangement is that of the RRTM (which is used in ecRad code and sub). 
