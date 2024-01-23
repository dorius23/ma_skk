Explanation of files and variables

**calving_events.csv**
This file contains the analyzed calving events and the corresponding identified precursor crevasses.

id - identifier of the calving event<br>
first_img_after - first cloud-free sentinel-2 image after the event<br>
last_img_before - last cloud-free sentinel-2 image before the event<br>
event_date - event date from sentinel-1 imagery or when not available average of dates of sentinel-2 images before/after<br>
pdd - positive degree days based on temperature data from ilulissat airport (elev 29 meters a.m.s.l.)<br>
pdd_max - total positive degree days in the corresponding calendar year<br>
pdd_pct - position in the pdd season of the event based on the pdd at the time of the event and the max pdd<br>
area - calved area in square kilometers<br>
dist_terminus-zero - distance from the calving front to the pre-defined zero point in meters<br>
pc_location - location of the precursor crevasse on the glacier terminal zone<br>
pc_fv - days before the calving event on which the precursor crevasse became first visible on sentinel-2 imagery<br>
pc_len_fv - lenght of the precursor crevasse as it became first visible<br>
pc_len_end - length of the precursor crevasse shortly before the calving event<br>
delta_len - change in length of the precursor crevasse<br>
dist_pcfv-terminus - distance of the precusor crevasse from the calving front at the time it became first visible<br>
pc_speed - propagation speed of the precursor crevasse<br>
group - grouping of the calving events by front position (1 is closest to the zero point, 4 is furthest)<br>
<br>

**lake_area.csv**
This file contains the automatically calculated lake areas of the 12 selected lakes, after the manual removal of outliers

date - calendar day
temp - temperature in degrees centigrade at ilulissat airport, corrected to an elevation of 780 meters a.m.s.l. using the standard temperature lapse rate<br>
pdd - positive degree days based on the temperature above<br>
ice_vel_front - velocity of the ice shortly before the calving front, in meters per day<br>
lkX_area - automatically calculated areas of the lakes 1 to 12, in square meters<br>
<br>

**drainage_events.csv**
This file contains a list of the manually identified lake drainage events, based on the lake areas from lake_area.csv

lake - identifier of the lake
start_date - start date of the event based on sentinel-2 and sentinel-2 imagery<br>
end_date - end date of the event based on sentinel-2 and sentinel-2 imagery<br>
start_area - area before the drainage event started in square meters<br>
end_area - area in the sentinel-2 image recorded at the end date in square meters<br>
mid_season - 0 if the event happened at the end of the season, 1 if it after this event more data was recorded<br>
duration - calculated duration of the event in days<br>
type - rapid if shorter/equal than 4 days, otherwise slow<br>
area_loss - area loss in square meters<br>
area_loss_pct - area loss in percent, based on the area at the start of the event<br>
PDD_start - positive degree days at the start of the event, based on temperature data from ilulissat airport, corrected to an elevation of 780 meters a.m.s.l. using the standard temperature lapse rate<br>
PDD_eos - positive degree days at the end of the season of the corresponding year (same data source as the previous variable)<br>
PDD_pct - position of the event in the pdd season based on the two previous variables<br>
<br>

**Google earth Engine code**
The Google Earth Engine repository, containing all code used for the study is found at the following link (Google account required):
https://code.earthengine.google.com/?accept_repo=users/dhautle/master_thesis
