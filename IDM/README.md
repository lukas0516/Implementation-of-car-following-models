# Intelligent Driver Model
---
> The time-continuous _Intelligent Driver Model_ (IDM) is probably the simplest complete and accident-free model producing realistic acceleration profiles and a plausible behavior in essentially all single-lane traffic situations.

## Mathematical Description
$$\dot{v}=a\left[1-\left(\frac{v}{v_0}\right)^\delta-\left(\frac{s^*(v, \Delta v)}{s}\right)^2\right] $$

The acceleration of the Intelligent Driver Model is given in the form $\tilde a_{\text{mic}} (s,v,\Delta v)$ and consists of two parts, one comparing the current speed $v$ to the desired speed $v_0$, and one comparing the current distance $s$ to the desired distance $s^*$. The deisred distance

$$s^*(v,\Delta v) = s_0 + \max(0, vT + \frac{v \Delta v}{2 \sqrt{ab}}) $$

has an _equilibrium term_ $s_0 + vT$ and a _dynamical term_ $v \Delta v / (2 \sqrt{ab})$ that implements the "intelligent" braking strategy.


## Parameters
* When _accelerating on a free raod from a standstill_, the vehicle starts with the maximum acceleration $a$. The acceleration decreases with increasing speed and goes to zero as the speed approaches the desired speed $v_0$. The exponent $\delta$ controls this reduction: The greater its value, the later the reduction of the acceleration when approaching the desired speed.
* When _following a leading vehicle_, the distance gap is approximately given by the safefy distance $s_0 + vT$. The safety distance is determined by the time gap $T$ plus the minimum distacen gap $s_0$.
* When _approaching slower or stopped vehicles_, the deceleration usually does not exceed the comfortable deceleration $b$. The acceleration function is smooth during transitions between these situations.

Each parameter describes a well-defined property . For example, transitions between highway and city traffic, can be modeled by solely changing the desired speed. All other parameters can be kept constant, modeling that somebody who drives aggressively (or defensively) on a highway presumably does so in city traffic as well.

%  ![File structure](./images/documentation_figure.png "Title")

---
## References
```
@article{treiber2013traffic,
  title={Traffic flow dynamics},
  author={Treiber, Martin and Kesting, Arne},
  journal={Traffic Flow Dynamics: Data, Models and Simulation, Springer-Verlag Berlin Heidelberg},
  pages={983--1000},
  year={2013},
  publisher={Springer}
}
```
