# alpine3d-modeling

### current forcing data workflow
 1. `get_nldas2.py` to download all the hourly data
 1. `get_prism.ipynb` to download monthly Tair/Precip data
 1. `merge_nldas.py` to combine netcdf files and match extent/res of prism
 1. `compute_corrections.py` to calculate Tair/Precip corrections based on prism
 1. `compute_forcings.py` to calc/correct forcing variables and format for alpine3d
 1.  Run WindNinja to improve wind forcings https://weather.firelab.org/windninja/
 1.  Begin alpine3d

### REQ directories

├── computed_forcings       # final forcings for alpine3d
│   ├── ILWR                # longwave radiation
│   ├── ISWR                # shortwave radiation
│   ├── PSUM                # precip
│   ├── RH                  # relative humidty
│   ├── TA                  # air temp
│   ├── VW                  # wind vector
│   └── VW_ninja            # wind vector after running through wind ninja
├── dem                     # dem for model domain (0.001 degree) 
├── nldas                   # download location for loooong NLDAS aquisition
├── nldas_correction_prism  # correction factors found from prism
├── nldas_merged            # merging and aligning NLDAS to prism
├── prism_precip_nc         # converted using gdal and saved here
├── prism_precip_tif        # downloaded from GEE notebook
├── prism_tair_nc           # converted using gdal and saved here
├── prism_tair_tif          # downloaded from GEE notebook
├── snotel                  # SWE/temp/precip data for calibration later on
└── tmp                     # tmp folder used throughout this code
