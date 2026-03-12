Hollow windlass CAPA

## Problem
On 4MAR26 during lot 3 acceptance testing a tourniquet was found where a windlass failed after 220 Newtons of force. The windlass had split near the inner strap during testing. Upon failure the windlass was observed to be printed at less than 100% infill. 

AB, quality specailist, J and MJ operations specialists, were present at the time of the failure.

(see photo 1)

## Invesitgation

Upon the failure identification all work was stopped. 

It was found that the issue could be easily identified by shining a flashlight behind the windlass and seeing if light transmitted through the piece:

![failure mode when illuminated](<img src="defect_inspection.jpg" width="400">)

Usigng the illumination inspection method all tourniquets and unassembled windlasses, including quanantine parts, were inspected by AB and MJ on 04MAR2026 and 07MAR2026 for a total of two inspections for all parts. 22 affected windlasses were found. 

### Review of windlass videos from printers:

All print videos for all prints are saved locally on each printer. This is the case for lot 1-3 but may not be the case for future lots depending on the model of printers used in future lots. All print videos were retrieved from both printers and watched. Prints where windlasses were printed were moved to a folder for each printer and attached to this CAPA.

#### DMDM printer, brand- Bambu Model- X1. Operated by CB. 
![CBI_X1_Bambu_ptrinter.zip(CBI_X1_Bambu_ptrinter.zip)]

Two windlass print beds were found to have been printed hollow, the interior densitiy appears to be around %15 which is a default interal density setting for Bambu slicing software. Of the 2 print beds, 1 was verified to have failed during the print, verified both by the length of the video and confirmation by the operator. 

One print bed of 23 windlasses was observed to have printed to completion with <100% infill. - `video_2025-11-09_17-44-26_hollow.mp4`

#### DMDM printer, brand- Bambu Model- P1S. Operated by AB.
![DMDM_P1S_Bambu_printer_windlass_timelapse.zip(DMDM_P1S_Bambu_printer_windlass_timelapse.zip)]

No print beds were found to have been printed with <100% infill

### Lot review

Lot 2 and lot 3 records were reviewed in order to determine the extent of exposure. Lot 1 was not reviewed due to the date of the print (09NOV2025) falling outside of the last lot 1 prodcution.

Lot 2 productions falls within the time frame where the non-conforming parts were in the production environment (09NOV2025 - 04MAR2926).

Lot 2 batch records were reviewed to determine if any batches had windlasses installed prior to the date of the non-conforming print ![dmdm_batch_records_07_MAR_2026.csv(dmdm_batch_records_07_MAR_2026.csv)]

The review of records shows lot 2 is unaffected by the non-conforming parts. As this non-conformance was indentified during final acceptance testing of lot 3, lot 3 was not released and therefore no lot 3 tourniquets were sent to customers. No recall is required at this time. 

### Investication conclusion

22 of 23 non-conforming parts were found and moved to quarantine. All lot 3 tourniquets and all part inventory were inspected twice leaving 1 outstanding non-conforming part. This part could not be located and was possibly discarded during initial part inspection due to an unrelated print defect or otherwise misplaced. The double 100% inspection and the confirmation of lot 2 being excluded from the affected popultion ensures the remaining unaccounted part has not and will not be sent to a customer. 

## Corrective action

The Glia tourniqet design specifies 100% infill for all printed parts ![GLIA Toruniquet instructions and specifications(https://github.com/GliaX/tourniquet/tree/master/assembly_instructions)]

The non-conforming windlasses appeared to have been printed around 15% infill which is consistant with the default bambu slicer settings. The current process for printing parts consists of downloading project files from [DMDM/print_files] which are version controlled. It is likely that when CB opened the project file the Bambu slicer reset to the default settings which resulted in the windlasses printing at <100%. 

- Instead of using project files, print beds should be converted to GCODE or otherwise locked down so no changed can by made by the user or software. The exisitng version control print settings should still be used.

- Due to the identical outward appearance, identifying <100% is not possible during part intake inspections. Using the illumination test was acceptable for situations where the part was already integrated into the assembly, however illumination may not work for parts where the infill is <100% but >15%. Therefore, a method of inspection using a calibrated scale will be developed and deployed to quickly inspect for the correct infill.

## Corrective action implmenetation

- Print file standardization
>**Warning** NOT COMPLETE - No further printing activities allowed until implented

- Inspection process update
>**Warning** NOT COMPLETE - No printed parts shall be accepted until implemented

