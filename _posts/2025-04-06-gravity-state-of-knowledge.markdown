---
layout: post
title:  "Gravity state of knowledge"
date:   2025-04-06 09:54:30 +0100
categories: jekyll update
---
{% include analytics.html %}

# Recent Progress in Gravitational Physics (2015–2025)

## Measurements of the Gravitational Constant $G$

The Newtonian gravitational constant $G$ remains the least precisely known fundamental constant in physics. Over the past decade, multiple high-precision experiments (using torsion pendulums, torsion balances, beam balances, and atom interferometers) have yielded $G$ values that **scatter by about 0.05% (500 ppm)** – far exceeding their reported uncertainties [^40][^13]. This is illustrated in **Figure 1**, which compares recent $G$ determinations by method. Each experiment reports $G \approx 6.673$–$6.675\times10^{-11}$ m³/kg·s² with relative uncertainties on the order of $10^{-5}$ to $10^{-4}$ (tens of ppm), yet the results do not statistically agree [^7][^13].

![Figure 1: Recent precision measurements of the gravitational constant $G$. Points show the reported $G$ values (horizontal axis) from various experiments since the 1980s, grouped by measurement method. The error bars are the $1σ$ uncertainties. Colors/symbols indicate different experimental techniques (ToS: torsion pendulum time-of-swing; AAF: angular-acceleration feedback; compensation methods; free deflection; Fabry–Perot cavity; beam balance; cold-atom interferometry). The spread of results (roughly 50–500 ppm) far exceeds individual error bars, highlighting the inconsistency among measurements.)](https://example.com/path-to-image.png)

**Record-precision experiments:** In 2018, researchers in China performed two simultaneous measurements using torsion pendulums: one using the time-of-swing (period shift) method and another using an angular-acceleration feedback method [^7]. They obtained:

- $G = 6.674184(11)\times10^{-11}$ m³/kg·s²  
- $G = 6.674484(11)\times10^{-11}$ m³/kg·s²  

(uncertainty ~12 ppm). These results differ from each other by about $4\times10^{-5}$ (40 ppm), which is several times the stated uncertainty. Likewise, a 2014 cold-atom interferometry experiment found $G = 6.67191(99)\times10^{-11}$ m³/kg·s² (150 ppm uncertainty) [^16], noticeably lower than most torsion balance results.

**Systematics vs. new physics:** The prevailing view is that unknown systematic errors are the cause of the discrepancies, rather than real spatiotemporal $G$ variations [^13]. Experimenters have uncovered subtle systematics in past setups – for example, anelastic torsion fiber damping can bias the time-of-swing method by 100–300 ppm if uncorrected. A 2015 claim that $G$ measurements fluctuate periodically (correlated with Earth’s 5.9-year length-of-day cycle) [^8] was largely dismissed after timing corrections weakened the supposed correlation. CODATA’s recommended $G$ now reflects a conservative uncertainty (~$2\times10^{-4}$%) to account for this dispersion [^15].

## Gravity on Intergalactic Scales (Galaxy & Cosmic Tests)

### Galaxy rotation curves and MOND

Spiral galaxies exhibit flat rotation curves – star orbital speeds remain high at large radii, inconsistent with Newtonian decline. In GR, this implies massive dark matter halos. **Modified Newtonian Dynamics (MOND)** posits that below $a_0 \sim 1\times10^{-10}$ m/s², gravity deviates from Newton’s law.

Recent surveys (e.g., SPARC) confirm a **tight correlation** between observed centripetal acceleration $g_{\rm obs}=v^2/r$ and that predicted from baryonic matter $g_{\rm bar}$ [^46]. The **Radial Acceleration Relation (RAR)**:

$$
g_{\rm obs} \approx \sqrt{a_0\,g_{\rm bar}}, \quad (g \ll a_0)
$$

is empirically very tight and universal across galaxies. MOND reproduces this naturally, but it struggles to explain mass in **galaxy clusters** without additional matter. The **Bullet Cluster** provides a strong case for collisionless dark matter – gravitational lensing centers do not coincide with the X-ray luminous gas [^50].

### Gravitational lensing and relativistic tests

**Strong lensing** studies (e.g. by Collett et al. 2018 on galaxy ESO 325–G004) measured the post-Newtonian parameter $\gamma = 0.97 \pm 0.09$ [^19], consistent with GR ($\gamma = 1$). **Weak lensing surveys** (KiDS, DES) also show that gravitational lensing and galaxy dynamics follow GR's predictions when dark matter is included. Any effective variation in $G$ on Mpc scales must be <1%.

### Cosmological scale gravity

The **Planck 2018** results show $\Lambda$CDM fits CMB data well with constant $G$ and GR. The **GW170817** event established that $|v_{\rm gw} - c| / c < 10^{-15}$, ruling out wide classes of modified gravity models with anomalous GW speed [^38].

**Emergent gravity** (e.g., Verlinde 2016) offers a framework where gravity is an entropic force. It makes testable predictions, such as galaxy lensing profiles without dark matter. One study found consistency with KiDS data [^22], though emergent gravity lacks a full cosmological description and struggles on cluster scales.

## Gravitational-Wave Observatories and Local Gravity Stability

Gravitational wave detections (LIGO, Virgo, KAGRA) allow precise tests of strong-field and radiative gravity.

### Tests of GR

Binary black hole mergers (e.g. GW150914) match GR waveforms to within 10% in phase evolution [^29]. LIGO/Virgo has not detected:

- Any deviations in waveform phase
- Non-GR polarization modes
- Echoes or other exotic merger remnants

All observed GWs are consistent with GR predictions [^29].

### Propagation tests and $G$ variation

**GW170817** showed GWs and gamma-rays arrived within 1.74 s after 130 million years’ travel, implying $v_{\rm gw} \approx c$ to $<10^{-15}$ [^38]. This rules out dispersive propagation due to a graviton mass or modified dispersion.

Gravitational waveform analysis also constrains time-varying $G$. The neutron star merger GW170817 sets limits on $|\Delta G/G| \lesssim$ few % over 130 Myr [^27]. Future events will probe even tighter limits. Pulsar timing already restricts $\dot{G}/G \lesssim 10^{-12}$–$10^{-13}$ yr⁻¹.

### Graviton mass

Waveform dispersion analyses yield graviton mass limits: $m_g \le 1.76\times10^{-23}$ eV/$c^2$, implying a range $\lambda_g \gtrsim 10^{16}$ km [^48]. Thus, gravity appears to have **no short-range cutoff** on galactic or cosmic scales.

## Conclusion

- **$G$ remains difficult to measure precisely**; variations across experiments are likely due to systematics, not new physics.
- **GR holds at galactic and cosmological scales**, when dark matter and dark energy are included. Modified gravity models like MOND can fit galaxy data but struggle at cluster and cosmological levels.
- **Gravitational-wave data** confirm GR’s predictions for waveform shape, speed, and polarization. They also **severely constrain time variation of $G$ and graviton mass**.
- Overall, Einstein's General Relativity, with a constant $G$, **remains consistent with all experimental data** from laboratory to cosmic scales.

---

## References

[^7]: Li, Q., et al. (2018). Measurements of the gravitational constant using two independent methods. *Nature*, **560**, 582–588.  
[^8]: Anderson, J.D., et al. (2015). Measurements of Newton’s gravitational constant and the length of day. *EPL*, **110**, 1002.  
[^13]: Schlamminger, S., Gundlach, J.H., & Newman, R.D. (2015). Recent measurements of the gravitational constant as a function of time. *Phys. Rev. D*, **91**, 121101(R).  
[^15]: CODATA 2018 recommended values of the fundamental physical constants.  
[^16]: Rosi, G., et al. (2014). Precision measurement of the Newtonian gravitational constant using cold atoms. *Nature*, **510**, 518–521.  
[^19]: Collett, T.E., et al. (2018). A precise extragalactic test of General Relativity. *Science*, **360**, 1342–1346.  
[^22]: Brouwer, M.M., et al. (2017). First test of Verlinde’s theory of Emergent Gravity using weak gravitational lensing. *MNRAS*, **466**, 2547–2559.  
[^27]: Desai, S. (2018). Limit on the time variation of Newton’s constant using GW170817. *Mod. Phys. Lett. A*, **33**, 1850224.  
[^29]: Abbott, B.P., et al. (2016–2021). Tests of general relativity with GWTC-1 and GWTC-2 events. *Phys. Rev. Lett.*, *ApJL*, *CQG*.  
[^38]: Abbott, B.P., et al. (2017). GW170817: Observation of Gravitational Waves from a Binary Neutron Star Inspiral. *Phys. Rev. Lett.*, **119**, 161101.  
[^40]: Quinn, T., Speake, C., Parks, H., & Davis, R. (2013). The Newtonian constant of gravitation: recent measurements and related studies. *Philos. Trans. R. Soc. A*, **372**, 20140032.  
[^46]: McGaugh, S., Lelli, F., & Schombert, J. (2016). The Radial Acceleration Relation in Rotationally Supported Galaxies. *Phys. Rev. Lett.*, **117**, 201101.  
[^48]: Abbott, B.P., et al. (2016). Tests of gravitational-wave propagation and polarization in the LIGO–Virgo observations. *Phys. Rev. Lett.*, **116**, 221101.  
[^50]: Clowe, D., et al. (2006). A Direct Empirical Proof of the Existence of Dark Matter. *ApJ*, **648**, L109–L113.

