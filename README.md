# Pneumatic Particle Separation in a Variable-Diameter Pulsed-Airflow Separator

A particle-level model of the pulsated pneumatic separator of Zhu et al. (2021), which separates the aluminum and copper foils of crushed lithium-ion batteries. Air flows upward through a column with a variable-diameter section. Aluminum leaves at the top and copper falls to the bottom.

![Foils in the separator in steady and in pulsed air flow](separator_animation.gif)

## Interactive version

The multi-particle model also runs in the browser, written in JavaScript with the same equations as the notebook. It needs no installation.

**[Open the Pulsed Air Separator Lab](https://yogeshpanchalcodes.github.io/pneumatic-separation-model/)**

The page follows the same 200 foils in two columns, one with steady and one with pulsed air flow. The reader can change the air flow rate, the pulse strength and the pulse frequency, see at which settings the separator works, and compare the model with the measurements of Zhu et al. The video is at the end of the page.

## What is in this repository

| File | Content |
|---|---|
| `Project_Check_In_Final_Project.ipynb` | The project notebook with the model, the code and all results |
| `separator_animation.mp4` | Short video (82 s) that explains the separator, shows 200 foils in steady and in pulsed air flow at 70 m³/h, repeats the test at nine flow rates and compares the model with measurements |
| `separator_animation.gif` | The simulation part of the video, shown above |
| `index.html` | The interactive version of the model, the page linked above |
| `film_poster.jpg` | Still image that the interactive page shows before the video starts |

## The model in brief

- Force balance on each foil with drag, gravity, buoyancy, pressure-gradient force and added mass (Li et al., 2023).
- Drag law for foils from the equivalent diameter method of Zhu et al. (2021), checked against their measured suspension velocities.
- Prescribed air flow rate with an optional pulsation, a one-seventh power-law velocity profile across the pipe with the radial velocity required by continuity, and turbulent fluctuations scaled with the friction velocity.
- Multi-particle simulation with hard-sphere collisions and wall reflection, written in JAX.
- Recovery and grade of both products against air flow rate, compared with the measurements of Zhu et al.

## How to run

Open the notebook in Google Colab and choose Runtime > Run all. It needs only NumPy, SciPy, pandas, Matplotlib and JAX, which Colab provides. The run takes about 11 minutes on Colab's CPU runtime.

To use the interactive page offline, download the repository and open `index.html` in a browser.

## References

Zhu, X.; Zhang, C.; Feng, P.; Yang, X.; Yang, X. A Novel Pulsated Pneumatic Separation with Variable-Diameter Structure and Its Application in the Recycling Spent Lithium-Ion Batteries. *Waste Management* 2021, 131, 20–30.

Li, D.; Wang, L.; Wei, L.; Qu, Q.; Wang, J. A Study of the Dynamic Mechanism in Low-Rank Coal Separation with Varying-Diameter Pulsed Airflow Separator. *Coal Preparation Technology* 2023, 51 (2), 9–13.

The full reference list is in the notebook.
