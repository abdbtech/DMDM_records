# Lot 3 Acceptance Testing: Statistical Analysis and Clinical Standards Review

**Document type:** Internal technical memo
**Project:** DMDM / GLIA Open-Source Windlass Tourniquet
**Prepared:** March 2026
**Related CAPA:** CAPA-4 — Lot 3 Acceptance Testing

---

## 1. Background

This document summarises the statistical analysis of tourniquet performance data collected across Lots 1–3 of the DMDM/GLIA windlass tourniquet, using the University of Western Ontario (UWO) open-source tourniquet tester as the test platform. It also documents a systematic review of the clinical and regulatory standards landscape, undertaken to establish an evidence-based acceptance criterion.

Predicate devices tested alongside DMDM units were the **North American Rescue Combat Application Tourniquet (CAT Gen 7)** and the **SAM Medical SAM XT**, both of which are CoTCCC-recommended and cleared for use.

---

## 2. Test Platform

All data were collected using the **UWO open-source tourniquet tester** (Liu et al., *HardwareX*, 2023). This platform uses a load cell connected to an Arduino microcontroller to record the force generated on a simulated limb at each quarter-turn of the windlass. Output is converted to pressure using a surface area calibration factor (*s*-value) specific to each test session.

To our knowledge, this is the first publicly documented, fully replicable mechanical test platform for windlass tourniquets. It stands in contrast to the proprietary HapMed Leg Tourniquet Trainer used in most published predicate evaluations, which applies a proprietary algorithm for blood loss estimation and does not publish pressure specifications.

### 2.1 Calibration variability

A persistent finding across sessions is that raw output values differ in magnitude between dates even for the same device. Analysis of the raw JSON and session metadata indicates that some sessions output pressure directly in mmHg (s-value applied in firmware) while at least one session (18 March 2026) output raw force in Newtons, requiring manual conversion:

```
P [mmHg] = F [N] / (133.32 × s_value)
```

This is consistent with a suspected inter-session firmware configuration difference in the Arduino software. All cross-session comparisons in this analysis use **within-session normalisation** (ratio of DMDM peak to same-session predicate peak) to eliminate this confound.

---

## 3. Findings: Pressure-Turn Behaviour

Across all devices and all sessions — DMDM Lots 1–3, NAR CAT, and SAM XT — the pressure-turn curves follow a consistent pattern:

1. Pressure rises with each quarter-turn of the windlass.
2. Pressure peaks, typically between 1.25 and 2.5 turns depending on device and limb simulator configuration.
3. Pressure declines slightly (5–15%) in the final quarter-turn before the windlass can no longer rotate.

**This pattern is identical across DMDM and predicate devices.** The NAR CAT's ability to complete more turns than the DMDM is not an advantage; it increases application time without a corresponding pressure benefit and has been noted as operationally undesirable in field settings where rapid application is critical.

The observation that backplate components cracked in some Lot 3 units does not disrupt this pressure curve. In all cases where a backplate crack was noted, the device continued to generate and maintain pressure through the strap and windlass mechanism. These are classified as **non-critical structural observations**, not functional failures.

**Windlass failures** (Lot3\_2 and Lot3\_7) are categorically different: a bent or fractured windlass rod may be unable to maintain the twisted state of the strap, potentially causing pressure loss. These units are excluded from the primary acceptance analysis and are treated as critical failures requiring root cause investigation.

---

## 4. Critical Finding: No Validated Clinical Floor Exists for Field Windlass Tourniquets

### 4.1 The 250 mmHg convention and its origins

The widely cited minimum effective tourniquet pressure of **250 mmHg** originates from the pneumatic surgical tourniquet literature, where it was used as a conservative fixed inflation pressure for elective upper-limb surgery in normotensive adults. It is not derived from field tourniquet performance data and has not been validated for windlass-type emergency tourniquets.

### 4.2 What the surgical literature actually shows

Contemporary surgical literature consistently demonstrates effective arterial occlusion at pressures well below 250 mmHg when tourniquet pressure is individualised to limb occlusion pressure (LOP):

- A 2025 systematic review and meta-analysis found a mean effective tourniquet inflation pressure of **169.3 mmHg** (95% CI: 144.9–193.6) across studies using LOP-based protocols, with a bloodless surgical field achieved in all cases.¹
- Arterial occlusion on the **thigh** averaged **229 mmHg** (SD 32, range 165–302) and on the **upper arm** averaged **140 mmHg** (SD 17, range 106–175) in cadaveric and clinical studies.²
- A randomised controlled trial in carpal tunnel surgery found an LOP-based group mean of **191 ± 14 mmHg** was equally effective to the standard 250 mmHg protocol.³
- Adaptive pneumatic systems have demonstrated mean arterial occlusion pressures of **152 mmHg** in normotensive patients.⁴

Higher fixed pressures have been associated with increased post-operative neural and soft tissue complications without efficacy benefit.

### 4.3 Field tourniquet validation methodology

Published evaluations of the CAT Gen 7 and SAM XT use the **HapMed Leg Tourniquet Trainer** to simulate an above-knee amputation and measure applied pressure, blood loss estimation, and application time.⁵ ⁶ A SAM Medical white paper comparing the SAM XT 700 and CAT Gen 7 reports an effective threshold of **500 mmHg** on the HapMed platform.⁷

This 500 mmHg figure reflects the mechanical load required on the HapMed simulator — a rigid training aid — and cannot be directly compared to physiological limb occlusion pressure. The HapMed's specifications, algorithms, and pressure sensor methodology are not publicly available. No ANSI or ISO standard currently governs windlass tourniquet performance testing or specifies a minimum acceptable pressure output.

**In short: the predicate devices are validated against a proprietary simulator with no published specifications and no regulatory pressure floor. The UWO tester is the first documented open replicable test platform for this device class.**

### 4.4 Grey area evidence

Informal testing conducted by trained EMTs applying DMDM and predicate devices to themselves and confirming distal pulse absence via palpation has demonstrated subjective occlusion at pressures that appear to be considerably below 250 mmHg. While this data is not formally documented, it is directionally consistent with the surgical LOP literature and supports the conclusion that 250 mmHg is a **conservative** floor for most patients.

---

## 5. Non-Inferiority Framework

### 5.1 Rationale

Given the absence of a validated absolute pressure floor for field windlass tourniquets, the most defensible acceptance strategy is to demonstrate that DMDM Lot 3 is **non-inferior** to cleared predicate devices by a pre-specified margin. This approach mirrors the FDA's framework for non-inferiority clinical trials (FDA Guidance, November 2016),⁸ adapted for a single continuous mechanical endpoint rather than a clinical outcome.

The framework is appropriate here because:
- A placebo-controlled design is not possible (an ineffective tourniquet is the "placebo" and is clearly harmful).
- A single validated surrogate endpoint exists (peak occlusion pressure on a standardised platform).
- The predicate effect vs. no-treatment is estimable.
- A clinical minimum can be reasonably specified even if imprecise.

### 5.2 Margin derivation

Using 250 mmHg as a conservative clinical floor and the NAR CAT mean peak from Lot 3 test sessions (≈ 314 mmHg) as the predicate reference:

```
Acceptable loss  = 314 − 250 = 64 mmHg
δ (NI margin)    = 64 / 314  = 20.4%
NI threshold     = 1 − δ     = 0.796
```

This means: a DMDM unit is acceptable if it achieves ≥ 79.6% of the same-session predicate peak. At this threshold, the device still reaches ≥ 250 mmHg. The threshold is expressed as a ratio rather than an absolute pressure to cancel out inter-session calibration differences.

Note that this margin is inherently conservative. If the true clinical floor is closer to 200 mmHg (supported by the LOP literature), the acceptable loss widens and the NI threshold tightens closer to 1.0 — making it easier to pass, not harder.

### 5.3 Predicate consistency

For the NI threshold to be meaningful, the predicate must perform consistently across sessions. Analysis of NAR CAT peaks in the two Lot 3 test sessions (8 March 2026: 315 mmHg estimated; 18 March 2026: 313 mmHg estimated) shows a **coefficient of variation < 1%** — the predicate is highly consistent in sessions where it was directly compared to Lot 3 units. This supports treating 314 mmHg as a stable reference.

NAR measurements from January 2025 (420–460 mmHg estimated) are substantially higher, which is consistent with the suspected firmware configuration difference producing non-comparable absolute values. Within-session normalisation eliminates this artefact.

---

## 6. Lot 3 Performance Summary

| Unit | Session | Notes | Ratio vs predicate |
|---|---|---|---|
| Lot3\_1 | 08Mar26 | No failure | ~0.84 |
| Lot3\_2 | 08Mar26 | Windlass failure at 1.75 turns | excluded |
| Lot3\_3 | 08Mar26 | No failure | ~0.80 |
| Lot3\_4 | 08Mar26 | No failure | ~0.83 |
| Lot3\_5 | 08Mar26 | No failure | ~0.81 |
| Lot3\_4 | 09Mar26 | Backplate crack (non-critical) | ~0.98 |
| Lot3\_5 | 09Mar26 | No failure | ~0.95 |
| Lot3\_6 | 09Mar26 | No failure | ~0.95 |
| Lot3\_7 | 18Mar26 | Windlass bend + backplate (critical) | excluded |
| Lot3\_8 | 18Mar26 | No failure | ~0.93 |
| Lot3\_9 | 18Mar26 | Near-zero pressure (statistical outlier) | requires investigation |

Excluding windlass failures and the Lot3\_9 outlier, the remaining Lot 3 units have a mean ratio of approximately **0.87–0.95** against same-session predicates. At δ = 20.4%, the threshold is 0.796. **All non-excluded units pass this criterion.**

Lot3\_9 is an unexplained outlier producing near-zero pressure even when corrected for the alternative s-value applied to that session. This unit requires physical inspection and root cause analysis before any conclusions can be drawn about it.

---

## 7. Limitations

- **Small sample sizes.** Lot 3 has n = 9–11 units across sessions. Statistical power is limited and p-values should be interpreted cautiously. Results are appropriate for internal lot release and CAPA support, not formal regulatory non-inferiority claims.
- **Clinical floor is uncertain.** The 250 mmHg floor is a defensible but imprecise assumption borrowed from a different patient population and device type. A prospective study correlating DMDM pressure output with distal pulse abolition in volunteer subjects would substantially strengthen this analysis.
- **Firmware calibration issue is unresolved.** Until the Arduino software configuration difference is identified and standardised, absolute cross-session comparisons remain uncertain. All future tests should log firmware version and verify units at session start using a known reference.
- **No validated standard exists.** The absence of an ANSI/ISO standard for windlass tourniquet mechanical performance means this analysis cannot reference a recognised acceptance criterion. It is constructed from first principles using the best available evidence.

---

## 8. Conclusions

1. DMDM Lot 3 units produce pressure curves consistent in shape with predicate devices. The peak-then-decline pattern is a property of windlass mechanics, not a defect.
2. Backplate cracking in Lot 3 is a non-critical structural observation that does not affect pressure generation or maintenance.
3. Two units with windlass failures (Lot3\_2, Lot3\_7) and one unexplained outlier (Lot3\_9) require root cause investigation and should not be released.
4. The remaining Lot 3 units meet a non-inferiority criterion of δ = 20.4% relative to same-session NAR CAT performance, where this margin is derived from a 250 mmHg conservative clinical floor.
5. The 250 mmHg floor itself is almost certainly conservative: contemporary surgical LOP literature demonstrates reliable arterial occlusion at 140–229 mmHg depending on limb. No validated floor exists specifically for field windlass tourniquets.
6. Predicate device manufacturers validate against a proprietary, non-published simulator. The UWO tester used here provides superior methodological transparency and replicability.

---

## References

1. Systematic Review and Meta-Analysis of Tourniquet Pressures in Upper Limb Surgery. *Journal of Clinical Medicine*, 2025. https://www.mdpi.com/2077-0383/14/6/1938
2. McEwen, J.A. Surgical Tourniquet Technology Adapted for Military and Prehospital Use. NATO RTO-MP-HFM-109, 2004. https://www.delfimedical.com/wp-content/uploads/2013/07/MP-HFM-109-P-19-McEwen.pdf
3. Limb Occlusion Pressure Versus Standard Tourniquet Inflation Pressure in Minor Hand Surgery: A Randomized Controlled Trial. *Journal of Orthopaedic Surgery and Research*, 2023. https://pmc.ncbi.nlm.nih.gov/articles/PMC10386602/
4. Development of Adaptive Pneumatic Tourniquet Systems Based on Minimal Inflation Pressure for Upper Limb Surgeries. *BioMedical Engineering OnLine*, 2013. https://link.springer.com/article/10.1186/1475-925X-12-92
5. Assessing the Current Generation of Tourniquets. *PubMed*, 2020. https://pubmed.ncbi.nlm.nih.gov/32091602/
6. COMBAT-C: Control of Major Bleeding by Application of Tourniquets over Clothing. *PMC*, 2024. https://pmc.ncbi.nlm.nih.gov/articles/PMC11141013/
7. Equivalence of SAM XT 700 and CAT Gen 7 Tourniquets. SAM Medical White Paper. https://rescue-essentials.com/content/XT%20700%20White%20Paper.pdf
8. FDA Guidance for Industry: Non-Inferiority Clinical Trials to Establish Effectiveness. November 2016. https://www.fda.gov/media/78504/download
9. Limb Occlusion Pressure (LOP). tourniquets.org. https://tourniquets.org/limb-occlusion-pressure-lop/
