#### liq_cloud_opt_param

This repository allows the verification of the fits used to derive the parameterizations included in the paper "Uncertainty of SW cloud radiative effect in atmospheric models due to the parameterization of liquid cloud optical properties" (E.Jahangir et al.) submitted to JAMES journal.
XXX files contain the coefficients of the fits explained in the section 3.3 of the paper. 
The reference Single Scattering Properties calculated with the Lorenz-Mie method for 4 shapes of Lognormal distribution function and with 9 spectral averaging methods on 80 effective radii ranging between 1 and 50 micro meters and tabulated in netCDF file called Ref_Log.nc.
This netCDF file encompasses the three SSPs:Qext, g and Single scattering albedo(SSA)
Each of variables are defined by 2 attributes : effective radius (r_eff) with dimension of 80 presenting the firs element being 0 and the last 80 micrometer Log DSD shape (presented by sigma) with dimension of 4



Note that the band arrangement differes from that of the RRTM (which is used in ecRad code and sub)
