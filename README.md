# predictTerrainMatchingUncertainty
In the geometry-based applications of ICESat-2 (ATLAS), the terrain matching, which registers the laser altimetry data with other sources of topographic data, conducts as a effective approach for accuracy verification or multiple data registration. We derive a theoretical uncertainty model linking performance with the main influence factors.

%%  Uncertainty prediction model for terrain matching method
%
%   The proposed uncertainty prediction model achieves a theoretical approach 
%   to calculate the uncertainty of terrain matching results.
%
%   ---------------------------
%   function [UncertaintyX, UncertaintyY, UncertaintyZ] = predictTerrainMatchingUncertainty(...
%       atlRandomVarianceX, atlRandomVarianceY, atlRandomVarianceZ, atlFootprintsNumber, ...
%       demResolutionX, demResolutionY, demVerticalAccuracy, ...
%       Ex1, Ex2, Ex3, Ex4, ...
%       Ey1, Ey2, Ey3, Ey4)
%
%
%   EXAMPLE
%   ---------------------------
%
%   [UncertaintyX, UncertaintyY, UncertaintyZ] = predictTerrainMatchingUncertainty(...
%       atlRandomVarianceX = 1.0, atlRandomVarianceY = 1.0, atlRandomVarianceZ = 0.5, atlFootprintsNumber = 1000, ...
%       demResolutionX = 1.0 (m), demResolutionY = 1.0 (m), demVerticalAccuracy = 0.1 (m), ...
%       Ex1 = 0.05, Ex2 = 0.2, Ex3 = 0.1, Ex4 = 1.0, ...
%       Ey1 = 0.05, Ey2 = 0.2, Ey3 = 0.1, Ey4 = 1.0)
%
%
%   USER INPUTS
%   ---------------------------
%
%     atlRandomVarianceX, atlRandomVarianceY, atlRandomVarianceZ  —  The magnitudes of horizontal and vertical random errors in the laser altimetry data
%     
%     atlFootprintsNumber  —  The number of the valid laser footprints of the laser altimetry data.
%
%     demResolutionX, demResolutionY  —  The horizontal resolutions of the DEM are directly provided by the DEM. 
%
%     demVerticalAccuracy  —  The vertical accuracy of the DEM are directly provided by the DEM. 
%
%     Ex1–Ex4, Ey1–Ey4  —  The statistical characteristics of the ground slope in the study site, 
%                          i.e., the first to fourth moments of elevation gradients, can be calculated from the used reference DEM.
%
%
%   OUTPUTS
%   ---------------------------
%
%     UncertaintyX, UncertaintyY, UncertaintyZ  —  The uncertainties of the estimated geolocation biases in x, y, and z directions.
%
%
