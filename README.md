# 2-Stage-OTA-Design

**The design requirements were as follows:**
- **ACL(s) = 2 (in-band gain for the closed-loop system)**
- **ω−3dB (upper bandwidth limit for the closed-loop system) = 2π * 15 * 10^6 rad/s**
- **Slew Rate = 30 V/μs**
- **Phase Margin > 70°**

The implementation of a CMOS OPAMP that combines a considerable dc gain with a
high unity gain frequency is a challenge. The approach to this design has been by hand
calculating and evaluating the deduced equations from the behavioral characteristics of NMOS
and PMOS transistors followed by simulations using 180nm technology on Cadence.

As per the given constraints for the circuit to be designed, it was supposed to be designed
for a feedback factor β = C1/(C1+C2) = 1/2. To achieve a closed loop gain of ACL = 2 with the given
β factor the circuit is supposed to have a very high open loop gain of the order of approximately
102 ~ 106or higher.

High gain being a major requirement of the system, a 2-stage Operational Transconductance Amplifier (OTA) topology,
which offers many advantages over its counter parts, has been chosen for the design.

For a closed loop system the upper bandwidth limit is multiplied by the feedback factor, i.e.,
Unity Gain Bandwidth Product (GBW) = feedback factor (β) * ω -3dB(given)
Hence, GBW = 2*2*pi*15*10^6.

To meet the requirements of Phase Margin (PM) and stability for the circuit, the concept of
Pole splitting was incorporated in the design using a compensation capacitor CC between first
and second stages of the amplifier.

Process parameters like μCox, Vth, Input common mode ranges (ICMR min and max) for both
NMOS and PMOS transistors were determined by pre-design simulations.

