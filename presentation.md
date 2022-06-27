# Instructor Onboarding for Data Carpentry: Image Processing with Python (beta)
<style>
    .reveal h1 { font-size: 2em; }
    .reveal h2 { font-size: 1.5em; }
</style>

Robert Turner, Image Processing with Python maintainers

August, 2022

# Welcome

# Why teach this course?

# What's in the course?

# Setup

# [Ep 1. Introduction](https://datacarpentry.org/image-processing/01-introduction/index.html)

- What research questions can we answer with image processing?
  - e.g. [imaging a Black Hole](https://iopscience.iop.org/article/10.3847/2041-8213/ab0e85), [estimating the population of Emperor Penguins](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3325796/), [the global-scale analysis of marine plankton diversity](https://www.cell.com/cell/fulltext/S0092-8674(19)31124-9), [segmentation of liver and vessels from CT images](https://doi.org/10.1016/j.cmpb.2017.12.008)
- Morphometrics

# [Ep 2. Image Basics](https://datacarpentry.org/image-processing/02-image-basics/index.html)

<!--This section warrants more time - people will probably get the Python stuff.-->

- Representation of images in computers.
- Images, arrays and pixels.
- How RGB is used to make colour images.
- File formats and compression.

# Image Representation

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard.png" alt="RGB Image" width="250"><br><p>RGB Image</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-red-channel.png" alt="Red channel" width="250"><br><p>Red channel</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-green-channel.png" alt="Green channel" width="250"><br><p>Green channel</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-blue-channel.png" alt="Blue channel" width="250"><br><p>Blue channel</p></td>
    </tr>
</table>

# [Ep 3. Working with skimage](https://datacarpentry.org/image-processing/03-skimage-images/index.html)

- `skimage` (Scikit Image)
  - Input + Output (images are not stored in `numpy` friendly formats)
  - Do weird things with arrays (e.g. `skimage.transform.resize`)
- `numpy`
  - Conventional array stuff (e.g. sub-setting, find all values `> x`)

# [Ep 4. Drawing and Bitwise Operations](https://datacarpentry.org/image-processing/04-drawing/index.html)

- Creating images from nothing
- Masking (setting pixels to be ignored)

# [Ep 5. Creating Histograms](https://datacarpentry.org/image-processing/05-creating-histograms/index.html)

- The distribution of intensity of colour in an image can tell us things.

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/data/plant-seedling.jpg" alt="Plant Seedling" width="250"><br><p>Plant Seedling</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/plant-seedling-colour-histogram.png" alt="Histogram" width="250"><br><p>Histogram</p></td>
    </tr>
</table>
