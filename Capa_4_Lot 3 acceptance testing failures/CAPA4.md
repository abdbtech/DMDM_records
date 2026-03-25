## Problem

During acceptance testing of TQ1 lot 3 08MAR26, the clinical limit, 250mmHg, set during the pre lot 1 production run as an acceptance criteria was met by all 6 test articles, however all 6 articles did not exceed the test limit by the same margin as lot 2 or lot 1. Testing against predicate devices, NAR CAT and SAM tourniquets showed similar performance indicating a possible issue with the test method. 

A separate issue was identified where the windlass of a lot 3 tourniquet shattered after the clinical limit was reached. This constitutes a critical failure that could lead to injury or death. Several other mechanical failures were recorded during subsequent testing, however none of these failures are considered critical and are consistent with historical failures when testing above the clinical limit. 

## Immediate response

Due to the ambiguous results, including the predicate test articles, and the critical windlass failure, it was decided by quality specialist AB and operations specialists MJ and JK that lot 3 was immediately quarantined and would not be distributed until further review. The issue was found during final lot acceptance testing, no lot 3 tourniquets were distributed to any customers, however several were possibly taken by specialists and members for non use demonstration units. 
Test methodology and background

All data was collected using the UWO tourniquet tester [1]. This tester uses a loadcell connected to an arduino which records the force generated on a simulated limb at each quarter turn of the windlass. Output is converted to pressure using a surface area calibration factor (S-value) specific to each test session. The initial load cell calibration is performed using a NIST 100g weight SN 1587.

Across all devices and all historical test sessions, the pressure per quarter turn follows a consistent curve where the pressure rises, peaks, then falls slightly just before the mechanical limit is reached. In all cases the tourniquet is tested until the operator can no longer turn the windlass, either due to physical strain or mechanical failure. In cases where there was a non-critical failure (backplate failure, windlass deformation) the pressure curve does not appear to be disrupted.

## Historical tourniquet testing

The acceptance criteria of 250mmHg was based on the limited clinical data available at the time. This limit originates from pneumatic surgical tourniquet literature, as non-pnumatic field application tourniquet data was (and still is not) available at the time. CoTCCC evaluates field tourniquets using a multi-parameter scoring system, including pressure measurement but they admit:

"There has not been a specific optimal tour-
niquet pressure range established, but multiple studies have
held that a range of 180 to 500mmHg can adequately occlude
arterial flow." [6]


Review of literature shows effective arterial occlusion at pressures well below 250mmHg:

- A 2025 systematic review and meta-analysis found a mean effective tourniquet inflation pressure of 169.3 mmHg, with a bloodless surgical field achieved in all cases.[2]

- Arterial occlusion on the thigh averaged 229 mmHg and on the upper arm averaged 140 mmHg in cadaveric and clinical studies.[3]

- A randomised controlled trial in carpal tunnel surgery found an LOP-based group mean of 191 ± 14 mmHg was equally effective to the standard 250 mmHg protocol.[4]

- Adaptive pneumatic systems have demonstrated mean arterial occlusion pressures of 152 mmHg in normotensive patients.[5]

Higher fixed pressures have been associated with increased post-operative neural and soft tissue complications without efficacy benefit.
Predicate device test methodology

The only documented testing of CAT and SAM tourniquets was performed using a proprietary device, the HapMed Leg Tourniquet Trainer, which measures application time and estimated blood loss [7][8]. And ultrasonic measurement of blood flow on live human test subjects [6]. Testing using the HapMed device indicates 500mmHg as the target pressure, however this device likely uses direct pressure measured by the load cell and does not include deformable materials similar to human tissue like the UWO test device. The 500mmHg target is likely a structural target rather than a clinical target. HapMed is a proprietary device and there are no published methods detailing it’s operation. 

## Clinical floor acceptance criteria rationale

The purpose of the DMDM project is to provide safe and effective medical devices to communities in need while providing a replicable approach to community healthcare manufacturing. DMDM determined the UWO tester, in conjunction with comparing the TQ1 against predicate devices, using the median clinical target of 250mmHg was the best acceptance criteria as it is replicable, open and based on the most recent clinical data available. CoTCCC methodology is useful as a reference but is not replicable and uses closed hardware, software and methods which is counter to the DMDM purpose. 


## Testing 

### 25MAY26 UWO tester investigation testing



## References

[1] Liu, Dawei, et al. “Distributed Manufacturing of an Open-Source Tourniquet Testing System.” HardwareX, vol. 15, 1 Sept. 2023, pp. e00442–e00442, ncbi.nlm.nih.gov/pmc/articles/PMC10338363/, https://doi.org/10.1016/j.ohx.2023.e00442. Accessed 22 Apr. 2024.
[2] Systematic Review and Meta-Analysis of Tourniquet Pressures in Upper Limb Surgery. *Journal of Clinical Medicine*, 2025. https://www.mdpi.com/2077-0383/14/6/1938
[3] McEwen, J.A. Surgical Tourniquet Technology Adapted for Military and Prehospital Use. NATO RTO-MP-HFM-109, 2004. https://www.delfimedical.com/wp-content/uploads/2013/07/MP-HFM-109-P-19-McEwen.pdf
[4] Limb Occlusion Pressure Versus Standard Tourniquet Inflation Pressure in Minor Hand Surgery: A Randomized Controlled Trial. *Journal of Orthopaedic Surgery and Research*, 2023. https://pmc.ncbi.nlm.nih.gov/articles/PMC10386602/
[5] Development of Adaptive Pneumatic Tourniquet Systems Based on Minimal Inflation Pressure for Upper Limb Surgeries. *BioMedical Engineering OnLine*, 2013. https://link.springer.com/article/10.1186/1475-925X-12-92
[6]Montgomery, H. R., Hammesfahr, R., Fisher, A. D., Cain, J. S., Greydanus, D. J., Butler, F. K., Goolsby, C., & Eastman, A. L. (2019). 2019 Recommended Limb Tourniquets in Tactical Combat Casualty Care. Journal of Special Operations Medicine, 19(4), 27–27. https://doi.org/10.55460/hqdv-7sxn
[7] Assessing the Current Generation of Tourniquets. *PubMed*, 2020. https://pubmed.ncbi.nlm.nih.gov/32091602/
[8] COMBAT-C: Control of Major Bleeding by Application of Tourniquets over Clothing. *PMC*, 2024. https://pmc.ncbi.nlm.nih.gov/articles/PMC11141013/



### possible causes

In house vs external (CB vs AB) printers

Supplier (Bambu) material change


### Testing

build test lot. Lot 3 TEST where x touniuquets are made using parts from supplier A, supplier B and material A, material B.



