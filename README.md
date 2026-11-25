⚠️ These encoders were generated using the Coriolis processing chain and version 1.24 (version 03.09.2026) for ARGO_simplified_profile.

# Sprof generator in Matlab

For a Python implementation, checkout this repository: https://github.com/euroargodev/pysprof

## Mono-cycle files

This tool is a stand-alone version of the "nc_create_synthetic_profile" tool used at the Coriolis GDAC to generate mono-cycle synthetic profile (S-PROF) files (from C and B mono-cycle (C-PROF and B-PROF) files).

See http://doi.org/10.13155/55637 for details.



```matlab
% SYNTAX :
%  create_mono_cycle_synthetic_profile(varargin)
%
% INPUT PARAMETERS :
%   varargin :
%      - should be provided in pairs ('param_name','param_value')
%      - 'param_name' value is not case sensitive
%   'param_name' parameter values are (all mandatory)
%      - 'floatWmo'      : the WMO number of the float to process
%      - 'inputDirName'  : the top directory of input (C-PROF, B-PROF and META)
%                          NetCDF files
%      - 'outputDirName' : the top directory of output S-PROF generated files
%                          (should exist)
%
% OUTPUT PARAMETERS :
%
% EXAMPLE :
%    create_mono_cycle_synthetic_profile('floatWmo', '7902334', ...
%       'inputDirName', 'C:/Users/jprannou/DATA/DAC/Coriolis', ...
%       'outputDirName', 'C:/Users/jprannou/DATA/OUT')
%
% SEE ALSO :
% AUTHOR : Jean-Philippe Rannou (Capgemini) (jean.philippe.rannou@partenaire-exterieur.ifremer.fr)
```

### Original File content
```matlab
function create_mono_cycle_synthetic_profile(varargin)
function [o_inputError] = parse_input_param(a_varargin)
function print_help
function process_one_float(a_floatInputDir, a_outputDir)
function nc_create_synthetic_profile_(a_cProfFileName, a_bProfFileName, a_metaFileName, a_outputDir, a_bgcFloatFlag)
function [o_profData] = get_prof_data(a_cProfFileName, a_bProfFileName)
function [o_profDataStruct] = get_prof_data_init_struct
function [o_syntProfData] = process_prof_data(a_profData, a_profData, a_cProfFileName, a_bProfFileName, a_metaFileName, a_bgcFloatFlag)
function [o_profDataStruct] = get_synthetic_prof_data_init_struct
function create_synthetic_mono_cycle_file(a_floatWmo, a_profData, a_outputDir)
```

### File content from the Coriolis Argo decoder
The following functions are duplicated from Coriolis Argo decoder distribution to generate a stand-alone version of the current tool.

#### The following code is under the responsibility of Henry Bittig, <henry.bittig@io-warnemuende.de>

```matlab
function synthfull=ARGO_simplified_profile(varargin)
function S=lov_netcdf_pickprod(filename,varargin)
function [xcon,ycon,ind] = consolidator(x,y,aggregation_mode,tol)
```

#### The following code is under the responsibility of Jean-Philippe Rannou, (Capgemini) <jean.philippe.rannou@partenaire-exterieur.ifremer.fr>

```matlab
function [o_now] = now_utc
function init_default_values(varargin)
function [o_julDay] = gregorian_2_julian_dec_argo(a_gregorianDate)
function [o_ncData] = get_data_from_nc_file(a_ncPathFileName, a_wantedVars)
function [o_varFlagList] = vars_are_present_dec_argo(a_ncId, a_varNameList)
function [o_dataValues] = get_data_from_name(a_dataName, a_dataList)
function [o_attributeStruct] = get_netcdf_param_attributes_extended(a_paramName, a_floatNum)
function [o_attributeStruct] = get_netcdf_param_attributes(a_paramName)
function [o_ncDataAtt] = get_att_from_nc_file(a_ncPathFileName, a_wantedVarAtts)
function [o_present] = var_is_present_dec_argo(a_ncId, a_varName)
function [o_present] = att_is_present_dec_argo(a_ncId, a_varName, a_attName)
function [o_dataValues] = get_att_from_name(a_varName, a_attName, a_dataList)
function [o_institution] = get_institution_from_data_centre(a_dataCentre, a_printWarningFlag)
function [o_profQc] = compute_profile_quality_flag(a_qcFlags)
```

## Multi-cycle

This tool is a stand-alone version of the "nc_create_synthetic_profile" tool used at the Coriolis GDAC to generate multi-cycle synthetic profile (M S-PROF) file (from mono-cycle synthetic profile (S-PROF) files).

See http://doi.org/10.13155/55637 for details.

```matlab
% SYNTAX :
%  create_multi_cycle_synthetic_profile(varargin)
%
% INPUT PARAMETERS :
%   varargin :
%      - should be provided in pairs ('param_name','param_value')
%      - 'param_name' value is not case sensitive
%   'param_name' parameter values are (all mandatory)
%      - 'floatWmo'      : the WMO number of the float to process
%      - 'inputDirName'  : the top directory of input (S-PROF) NetCDF files
%      - 'outputDirName' : the top directory of output M S-PROF generated file
%                          (should exist)
%
% OUTPUT PARAMETERS :
%
% EXAMPLE :
%    create_multi_cycle_synthetic_profile('floatWmo', '7902334', ...
%       'inputDirName', 'C:/Users/jprannou/DATA/DAC/Coriolis', ...
%       'outputDirName', 'C:/Users/jprannou/DATA/OUT')
%
% SEE ALSO :
% AUTHOR : Jean-Philippe Rannou (Capgemini) (jean.philippe.rannou@partenaire-exterieur.ifremer.fr)
```

### Original File content
```matlab
function create_multi_cycle_synthetic_profile(varargin)
function [o_inputError] = parse_input_param(a_varargin)
function print_help
function process_one_float(a_floatInputDir, a_outputDir)
function [o_syntProfAllData] = get_all_synthetic_prof_data(a_floatInputDir)
function [o_syntProfData] = get_synthetic_prof_data(a_sProfFileName)
function [o_profDataStruct] = get_synthetic_prof_data_init_struct
function [a_syntProfAllData] = uniformize_n_calib_dimension(a_syntProfAllData)
function create_synthetic_multi_cycle_file(a_floatWmo, a_profData, a_outputDir)
```

### File content from the Coriolis Argo decoder
The following functions are duplicated from Coriolis Argo decoder distribution to generate a stand-alone version of the current tool.

#### The following code is under the responsibility of Jean-Philippe Rannou, (Capgemini) <jean.philippe.rannou@partenaire-exterieur.ifremer.fr>

```matlab
function [o_now] = now_utc
function init_default_values(varargin)
function [o_julDay] = gregorian_2_julian_dec_argo(a_gregorianDate)
function [o_ncData] = get_data_from_nc_file(a_ncPathFileName, a_wantedVars)
function [o_varFlagList] = vars_are_present_dec_argo(a_ncId, a_varNameList)
function [o_dataValues] = get_data_from_name(a_dataName, a_dataList)
function [o_ncDataAtt] = get_att_from_nc_file(a_ncPathFileName, a_wantedVarAtts)
function [o_present] = var_is_present_dec_argo(a_ncId, a_varName)
function [o_present] = att_is_present_dec_argo(a_ncId, a_varName, a_attName)
function [o_dataValues] = get_att_from_name(a_varName, a_attName, a_dataList)
function [o_attributeStruct] = get_netcdf_param_attributes_extended(a_paramName, a_floatNum)
function [o_attributeStruct] = get_netcdf_param_attributes(a_paramName)
function [o_institution] = get_institution_from_data_centre(a_dataCentre, a_printWarningFlag)
function [o_profQc] = compute_profile_quality_flag(a_qcFlags)
```
