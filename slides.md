---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

---

# Bibliography
<div id="refs"></div>

---

:::: {.columns}
::: {.column width="50%"}
### Distribution of Math Scores

This histogram visualizes the frequency distribution of math scores among students in the dataset.

- **X-axis**: Math Score
- **Y-axis**: Frequency
- **Binwidth**: 25

::: {.fragment}
The data shows a range of scores, with higher frequencies observed in the mid-range.
:::

:::

::: {.column width="50%"}
<iframe data-src='media/plots/math_score_histogram.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### X-bar Chart for PartLength

This chart monitors the process mean of `PartLength` using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/part_length_xbar_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength

This chart monitors the process variation (range) of `PartLength` using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/part_length_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength

This chart monitors the process variation (range) of `PartLength` using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/part_length_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Distribution of Math Scores

This histogram visualizes the frequency distribution of math scores among students in the dataset.

- **X-axis**: Math Score
- **Y-axis**: Frequency
- **Binwidth**: 25

::: {.fragment}
The data shows a range of scores, with higher frequencies observed in the mid-range.
:::

:::

::: {.column width="50%"}
<iframe data-src='media/plots/math_score_histogram.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### X-bar Chart for PartLength (Machine 1, 200kPa, 338K)

This chart monitors the process mean of `PartLength` specifically for `Machine 1` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_filtered_xbar_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 1, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 1` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 1, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 1` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 2, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 2` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine2_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 3, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 3` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine3_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 1, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 1` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 2, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 2` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine2_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### R Chart for PartLength (Machine 3, 200kPa, 338K)

This chart monitors the process variation (range) of `PartLength` specifically for `Machine 3` operating at `200kPa` pressure and `338K` temperature, using subgroups of 5 observations. The center line (CL), upper control limit (UCL), and lower control limit (LCL) are shown.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine3_filtered_r_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability Histogram: PartLength (Machine 1, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 1` operating at `200kPa` pressure and `338K` temperature. A normal distribution curve is overlaid to illustrate the process's inherent variability.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_capability_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability Histogram: PartLength (Machine 2, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 2` operating at `200kPa` pressure and `338K` temperature. A normal distribution curve is overlaid to illustrate the process's inherent variability.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine2_capability_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability Histogram: PartLength (Machine 3, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 3` operating at `200kPa` pressure and `338K` temperature. A normal distribution curve is overlaid to illustrate the process's inherent variability.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine3_capability_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Process Capability Histogram: PartLength (Machine 1, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 1` operating at `200kPa` pressure and `338K` temperature. A normal distribution curve is overlaid to illustrate the process's inherent variability.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_capability_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Process Capability Histogram: PartLength (Machine 2, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 2` operating at `200kPa` pressure and `338K` temperature. A normal distribution curve is overlaid to illustrate the process's inherent variability.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine2_capability_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Process Capability Histogram: PartLength (Machine 3, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 3` operating at `200kPa` pressure and `338K` temperature. A normal distribution curve is overlaid to illustrate the process's inherent variability.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine3_capability_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Process Capability (Cpk) Chart: PartLength (Machine 1, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 1`. It includes the Lower Specification Limit (LSL), Upper Specification Limit (USL), and the calculated Cpk value, providing a measure of process capability.

_Assumed Specification Limits: LSL=45, USL=55, Target=50 for illustrative purposes._
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine1_cpk_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Process Capability (Cpk) Chart: PartLength (Machine 2, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 2`. It includes the Lower Specification Limit (LSL), Upper Specification Limit (USL), and the calculated Cpk value, providing a measure of process capability.

_Assumed Specification Limits: LSL=45, USL=55, Target=50 for illustrative purposes._
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine2_cpk_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### Process Capability (Cpk) Chart: PartLength (Machine 3, 200kPa, 338K)

This chart visualizes the distribution of `PartLength` for `Machine 3`. It includes the Lower Specification Limit (LSL), Upper Specification Limit (USL), and the calculated Cpk value, providing a measure of process capability.

_Assumed Specification Limits: LSL=45, USL=55, Target=50 for illustrative purposes._
:::

::: {.column width="50%"}
<iframe data-src='media/plots/machine3_cpk_chart.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::
