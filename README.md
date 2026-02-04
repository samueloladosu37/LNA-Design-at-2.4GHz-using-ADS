# LNA Design at 2.4 GHz using ADS

Low Noise Amplifier (LNA) design implemented and simulated in **Keysight ADS** for the 2.4 GHz ISM band.

---

## LNA Design Specifications

- **Frequency Band:** 2.35 GHz – 2.45 GHz  
- **Gain:** > 14 dB  
- **Noise Figure (NF):** ≤ 1.4 dB  
- **Input Return Loss (S11):** < –15 dB  
- **Output Return Loss (S22):** < –15 dB  
- **P1dB:** > 10 dBm  
- **OIP3:** > 20 dBm  

---

## LNA Design Technology Options

1. **MMIC (GaAs pHEMT process)**  
   - High broadband performance  
   - Suitable for IC designers  

2. **PCB / MIC / RF Board**  
   - Good performance  
   - Low cost  
   - Easy tuning after fabrication  
   - Larger physical size  

3. **RFIC (Silicon / CMOS)**  

---

## Device Selection Criteria (RF Board LNA)

**Rule of thumb:**  
Choose a transistor whose **NFmin ≤ 0.5 × desired LNA NF**.

### Example used in this design:
- **Device:** ATF-211170  
- **NFmin:** 0.6 dB  
- **Gain:** ~12 dB  

The intrinsic noise figure of the transistor is less than half of the target LNA noise figure, making it suitable for low-noise design.

---

## LNA Impedance Matching Considerations

1. **Γopt** is the source reflection coefficient that yields **minimum NF**  
2. Noise matching may reduce gain  
3. **Γopt ≠ S11\*** → noise match ≠ gain match  
4. **Rn (noise resistance)** indicates noise sensitivity  
5. Output matching is typically **complex conjugate matching**  
6. Input matching is a trade-off between **NF** and **S11**  
7. For minimum NF:  
   - Γsource = Γopt  
8. For best return loss:  
   - Γsource = S11\*  

---

## DC Biasing and Operating Point

- LNAs are typically biased in **Class A**  
- Class A offers:
  - High linearity  
  - Stable operation  
- Efficiency is not a primary concern for LNAs  

### Biasing Methods:
- Use transistor datasheet Class-A operating point  
- Perform **DC sweep analysis** in ADS  

**Practical tip:**  
Bias the transistor at approximately **Idss / 2** for optimal linearity and noise performance.

---

## Tools

- **Simulation Tool:** Keysight Advanced Design System (ADS)  
- **ADS Version:** XX  

---

## How to Open the Project

1. Open **Keysight ADS**
2. Set the workspace to this project directory
3. Open the schematic:  
