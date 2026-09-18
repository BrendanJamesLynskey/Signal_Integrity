# ⬡ Signal Integrity & High-Speed Digital Design

Seventeen interactive slide decks on getting a signal from one chip to another intact — the physics of the channel, the mechanisms that close an eye, and the arithmetic a standard uses to decide a channel is legal.

## ▶ [Open the Series Landing Page](https://brendanjameslynskey.github.io/Signal_Integrity/)

**Every number on every slide is computed.** Each deck embeds the JSON output of a model in [`si_models`](https://github.com/BrendanJamesLynskey/Matrix_Articles), and nothing is typed in by hand. Where an independently published result exists, the model is checked against it and the disagreement is reported on the landing page.

---

## The decks

### The passive channel &mdash; decks 01&ndash;04

What a transmission line is, where the return current flows, what the materials do to the signal, and what happens at the one feature made by drilling.

| # | Deck | Slides | What it establishes |
|---|------|--------|---------------------|
| 01 | [The Transmission Line and the Physical Channel](https://brendanjameslynskey.github.io/Signal_Integrity/01-transmission-lines/) | 14 | Johnson and Graham's propagation-region breakpoints reproduced to 0.35 %; the two coaxial optima (76.7 &Omega; for minimum loss, 30 &Omega; for maximum power) derived rather than quoted; TDR shown under-reading a 38 &Omega; section as 44 &Omega; when it is shorter than the edge |
| 02 | [Return Paths and Reference Planes](https://brendanjameslynskey.github.io/Signal_Integrity/02-return-paths/) | 12 | The Lorentzian return-current law integrated to the 80 % / 3h rule (79.5 %) and checked against the field solver's own charge profile; a 20 mm plane slot priced at 13.7 nH and &minus;18.8 dB at 10 GHz |
| 03 | [Materials, Loss and Causality](https://brendanjameslynskey.github.io/Signal_Integrity/03-materials-and-loss/) | 13 | Hammerstad and Huray both reproduced against Hall and Heck's worked examples to 0.8 %; a constant-Dk model shown delivering energy 37 ps before the wave can arrive; fibre-weave skew anchored to a published measurement at 5.1 ps/inch |
| 04 | [Vias, Connectors and Discontinuities](https://brendanjameslynskey.github.io/Signal_Integrity/04-vias-and-discontinuities/) | 12 | A 110 mil stub's quarter-wave notch computed at 13.9 GHz, within a few per cent of a 28 GBd Nyquist; and the result that a barrel matched to the channel is *not* the best via &mdash; compensating the launch instead is worth 7&ndash;24 dB |

### The signal on it &mdash; decks 05&ndash;06

Why every fast link is differential, and the one impairment no equaliser can remove.

| # | Deck | Slides | What it establishes |
|---|------|--------|---------------------|
| 05 | [Differential Signalling](https://brendanjameslynskey.github.io/Signal_Integrity/05-differential-signalling/) | 12 | Cohn's exact coupled-stripline result reproduced to 0.18 %; half-ounce copper shown to lower a 100 &Omega; pair by 9.7 %; tight coupling priced at 1.45 dB over ten inches at 14 GHz |
| 06 | [Crosstalk](https://brendanjameslynskey.github.io/Signal_Integrity/06-crosstalk/) | 11 | The field solver gives L&#8320;/L = C&#8320;/C to six decimals in stripline, so far-end crosstalk vanishes exactly; far-end coupling shown to saturate at half the swing rather than growing without bound as the first-order formula predicts |

### Jitter &mdash; decks 07&ndash;10

Organised around Ransom Stephens's five rules: it is about the bit error ratio, total jitter can only be measured on a bit error ratio tester, measurement is always a comparison against a reference clock, and timing noise and amplitude noise are not really separable.

| # | Deck | Slides | What it establishes |
|---|------|--------|---------------------|
| 07 | [Total Jitter and the Bit Error Ratio](https://brendanjameslynskey.github.io/Signal_Integrity/07-total-jitter/) | 11 | Stephens's five rules as the spine. A confident measurement at 10&#8315;&#185;&#178; takes six minutes at 28 Gb/s and four days at 10&#8315;&#185;&#8309;; the real data-dependent distribution computed from the channel, and it is nothing like two impulses |
| 08 | [The Dual-Dirac Model and Its Limits](https://brendanjameslynskey.github.io/Signal_Integrity/08-dual-dirac/) | 11 | **DJ(&delta;&delta;) computed against the true peak-to-peak** &mdash; the model's deterministic jitter comes out 8&ndash;28 % *smaller* than the real spread, and the fitted random jitter 1.27&ndash;1.32&times; too large, because the fit absorbs smooth deterministic width |
| 09 | [Clock Recovery, the Reference Clock and Tolerance](https://brendanjameslynskey.github.io/Signal_Integrity/09-clock-recovery/) | 10 | Jitter transfer against error response, the golden PLL, and a tolerance mask shown to be the loop restated as a test; the same oscillator yielding jitter figures a hundredfold apart depending only on the integration band |
| 10 | [Crosstalk, Amplitude Noise and the Two-Dimensional View](https://brendanjameslynskey.github.io/Signal_Integrity/10-amplitude-noise/) | 10 | Rule four computed: a 1 mV disturbance is worth 0.17 ps on this channel, and amplitude-induced jitter rises **212&times;** from 1 to 56 Gb/s because the channel, not the transmitter, sets the edge &mdash; the knee falling at about 10 Gb/s, where Stephens put it from quite different reasoning |

### Power integrity &mdash; decks 11&ndash;14

The power delivery network as an impedance, as an ecology of resonances, as something that has to be measured in milliohms, and finally as a source of signal-integrity failures.

| # | Deck | Slides | What it establishes |
|---|------|--------|---------------------|
| 11 | [The Power Delivery Network as an Impedance](https://brendanjameslynskey.github.io/Signal_Integrity/11-pdn-impedance/) | 10 | Target impedance and its limits; the frequency-domain target-impedance method, which shows the **number of capacitors is set by mounting inductance and not by capacitance at all**; and adding capacitors of one value making the peak worse |
| 12 | [Planes, Cavities and the PDN Ecology](https://brendanjameslynskey.github.io/Signal_Integrity/12-planes-and-ecology/) | 10 | Spreading inductance, cavity impedance that depends on where you probe, and the **Bandini Mountain** &mdash; the antiresonance between on-die capacitance and package inductance that board capacitors cannot reach, with its optimum damping computed at the characteristic impedance |
| 13 | [Measuring Low Impedance](https://brendanjameslynskey.github.io/Signal_Integrity/13-measuring-low-impedance/) | 9 | Why a reflection measurement floors at about an ohm on directivity alone, how two-port shunt-through reaches a milliohm at &minus;88 dB, and the cable-braid ground loop that always reads *low* |
| 14 | [Power Integrity Meets Signal Integrity](https://brendanjameslynskey.github.io/Signal_Integrity/14-pi-meets-si/) | 10 | Four routes from the rail to the eye, and the observation that two of them are return-path problems rather than power problems; the worst supply-tone frequency computed to sit *on* the loop bandwidth for a type-II loop, while a type-I loop has no worst frequency at all &mdash; its response is flat |

### The verdict &mdash; decks 15&ndash;17

Whether the timing closes, whether the measurements can be believed, and how a standard turns all of it into a pass or a fail.

| # | Deck | Slides | What it establishes |
|---|------|--------|---------------------|
| 15 | [Timing, Flight Time and the Budget](https://brendanjameslynskey.github.io/Signal_Integrity/15-timing-and-budgets/) | 10 | Flight time shown to exceed propagation delay by 5&times; on a weakly driven line; statistical budgeting shown to save 47&ndash;67 % at 3&sigma; and &minus;24 % to +22 % at 10&#8315;&#185;&#178; |
| 16 | [Measurement, De-embedding and Correlation](https://brendanjameslynskey.github.io/Signal_Integrity/16-measurement-and-correlation/) | 11 | An identical reflection placed at different delays gives identical insertion-loss agreement (0.15 dB rms) and eye errors from +1.3 % to &minus;5.5 %; the DC point alone is worth 7.9 % of the eye |
| 17 | [Channel Operating Margin and Compliance](https://brendanjameslynskey.github.io/Signal_Integrity/17-com-and-compliance/) | 12 | COM on the SerDes_Equalisation channel passes at 11.96 dB while the same channel misses an uncoded 10&#8315;&#185;&#178; by 4.98 dB &mdash; reconciled by the pre-FEC error ratio the threshold assumes |

**188 slides across seventeen decks.** Single-page HTML, KaTeX-rendered maths, no build step — open any `index.html` directly.

## Long-form companion

The same material as a written report: [Signal_Integrity.pdf](Signal_Integrity.pdf) (32 pp). It carries the continuous argument where the decks carry the interactive models, and it is generated from the same computations, so a number cannot differ between the two.

---

## Verified

A model that agrees only with itself is not worth much. Every cross-check the series makes against an independently published result, followed by the places where two computations inside the series have to agree with each other:

| Quantity | This series | Reference value | Difference | Source |
|---|---|---|---|---|
| zdiff w0.15 s0.15 | 102.62 | 102.44 | +0.18 % | Cohn 1955, exact coupled-stripline result |
| zdiff w0.15 s0.30 | 112.32 | 112.39 | -0.06 % | Cohn 1955, exact coupled-stripline result |
| zdiff w0.20 s0.20 | 93.189 | 93.282 | -0.10 % | Cohn 1955, exact coupled-stripline result |
| f rough onset | 1.348e+09 | 1.34e+09 | +0.59 % | Hall & Heck, Advanced Signal Integrity, ch. 5 |
| hammerstad rac ratio | 1.7144 | 1.7284 | -0.81 % | Hall & Heck, Advanced Signal Integrity, ch. 5 |
| huray factor | 1.9579 | 1.95 | +0.40 % | Hall & Heck, Advanced Signal Integrity, ch. 5 |
| huray sphere area um2 | 160.9 | 161 | -0.06 % | Hall & Heck, Advanced Signal Integrity, ch. 5 |
| weave five inch ghz | 19.511 | 20 | -2.44 % | Hall & Heck, example 7-2 |
| weave ten inch ghz | 9.7557 | 10 | -2.44 % | Hall & Heck, example 7-2 |
| return within 3h | 0.79517 | 0.8 | -0.60 % | Johnson sec 5.2; Hall & Heck eq (5-15) |
| C | 6.917e-11 | 6.91e-11 | +0.10 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| L | 6.917e-07 | 6.91e-07 | +0.10 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| critical length m | 1.977 | 1.97 | +0.35 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| f diel | 4.9889e+08 | 4.98e+08 | +0.18 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| f lc | 9.5873e+06 | 9.58e+06 | +0.08 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| f skin | 2.7152e+07 | 2.71e+07 | +0.19 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| f wg | 1.423e+11 | 1.42e+11 | +0.21 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| r ac f0 | 76.742 | 76.74 | +0.00 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| r dc | 12.645 | 12.64 | +0.04 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| v0 | 1.4457e+08 | 1.4457e+08 | +0.00 % | Johnson & Graham, Advanced Black Magic 2003, sec 3.10 |
| droop vs zpeak | 23.241 | 24.876 | -6.57 % | internal: deepest transient droop per amp against the peak of the impedance profile (time domain vs frequency domain) |

Worst disagreement against published work: **2.44 %**.

---

## How the series is built

The decks are assembled from bodies and data rather than written as HTML by hand:

```
cd Matrix_Articles
python3 si_models/run_all.py      # computes every figure, writes _si_data/*.json
python3 assemble_si.py            # glues house style + body + data -> Signal_Integrity/
```

`si_models/fdm2d.py` is a two-dimensional electrostatic field solver used wherever a
closed form does not exist — coupled pairs beside guard traces, microstrip with air
above it, conductors with real thickness. It is validated against Cohn's exact
coupled-stripline result to better than half a per cent, which is what licenses using it
on the cross-sections Cohn does not cover.

`si_models/sparam_qc.py` and `si_models/com.py` import the channel from
[`serdes_model.py`](https://github.com/BrendanJamesLynskey/Matrix_Articles) read-only, so nothing published in
[SerDes_Equalisation](https://github.com/BrendanJamesLynskey/SerDes_Equalisation) is disturbed by anything computed here.

---

## Sources

The series reads widely and verifies independently; it does not reproduce. Where a
published worked example exists it is used as a check and cited, and the checks are
tabulated above.

- Howard Johnson and Martin Graham, *High-Speed Digital Design: A Handbook of Black
  Magic* (1993) and *High-Speed Signal Propagation: Advanced Black Magic* (2003) —
  propagation regions, via modelling, return paths, clock jitter
- Stephen Hall and Howard Heck, *Advanced Signal Integrity for High-Speed Digital
  Designs* (2009) — conductor roughness, causal dielectric models, the fibre-weave effect
- Eric Bogatin, *Signal and Power Integrity — Simplified*, 2nd ed. (2010) — return
  paths, differential pairs, power integrity
- Peter Pupalaikis, *S-Parameters for Signal Integrity* (2020) — de-embedding,
  passivity and causality
- Greg Edlund, *Timing Analysis and Simulation for Signal Integrity Engineers* (2007)
- Mark Horowitz, *High-Speed Electrical Signalling: Overview and Limitations*
- Seymour Cohn, *Shielded Coupled-Strip Transmission Line* (1955) — the exact result the
  field solver is validated against
- Eric Bogatin's [Signal Integrity Journal columns](https://www.colorado.edu/faculty/bogatin/publications/si-journal),
  Yuriy Shlepnev's [Simberian application notes](https://www.simberian.com/AppNotes.php),
  Donald Telian's [published work](https://siguys.com/published-works/), and the
  [SIJ Fundamentals blog](https://www.signalintegrityjournal.com/blogs/12-fundamentals)

---

## Related material

Indexed together under [Signal Integrity & High-Speed Digital Design](https://github.com/BrendanJamesLynskey/Hardware#signal-integrity--high-speed-digital-design) in the Hardware repo.

| Repo | How it relates |
| --- | --- |
| [Equalisation in High-Speed Serial Links](https://github.com/BrendanJamesLynskey/SerDes_Equalisation) | The worked 28.8 inch backplane channel this series keeps returning to, taken from S-parameters to a closed link budget. Decks 10 and 11 import it directly |
| [Matrix Methods in Network Parameters](https://github.com/BrendanJamesLynskey/Matrix_Methods_Network_Parameters) | The S-, Z- and Y-parameter algebra behind every cascade here — reciprocity, passivity, mixed-mode, causality, the Smith chart |
| [Matrix Concepts in Digital Filters](https://github.com/BrendanJamesLynskey/Matrix_Concepts_Digital_Filters) | The optimal-tap theory behind every equaliser in decks 10 and 11 |
| [Kramers–Kronig Relations](https://github.com/BrendanJamesLynskey/Kramers_Kronig_Relations) | The causality constraint deck 03 applies to a dielectric and deck 10 to a transfer function |
| [High-Speed Serial Links — interview preparation](https://github.com/BrendanJamesLynskey/Interview_High_Speed_Serial_Links) | The written companion covering the same ground in prose: link budgets, drivers, PLL jitter, CTLE/DFE/CDR, PCIe, UCIe, NVLink, eye analysis, crosstalk, PDN coupling |
| [LPDDRx Layout — interview preparation](https://github.com/BrendanJamesLynskey/Interview_LPDDRx_Layout) | The parallel-bus side of deck 09 — memory interface layout, skew and termination |
| [Modern SoC Design](https://github.com/BrendanJamesLynskey/SoC) | The silicon side. Deck 04 covers SerDes and I/O, deck 01 packaging, deck 09 power delivery (the complement to deck 07 here), deck 13 clocks and resets |
| [Arm AMBA](https://github.com/BrendanJamesLynskey/AMBA) | What the traffic becomes once it is on-chip |
| [Hardware](https://github.com/BrendanJamesLynskey/Hardware) | The index this series sits in |

---

Generated by `make_si_readme.py` from the same data the decks embed.
