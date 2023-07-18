# Image Processing with Python

Jacob Deppen and David Palmquist

Image Processing with Python maintainers

July, 2023

<style>
    .reveal h1 { font-size: 2em; }
    .reveal h2 { font-size: 1.5em; }
</style>

<script>
Reveal.initialize({ slideNumber: true });
</script>

# Thank you!

Thanks to Nisha and Mary for hosting and thank _you_ for coming.

# Presenters

- Jacob Deppen, `deppen8` on GitHub
- David Palmquist, `quist00` on GitHub

# Acknowledgements

- Current maintainer team: Kimberly Meechan, Ulf Schiller, Robert Turner, Toby Hodges
- Content originally developed by Mark Meysenburg, Tessa Durham Brooks, Dominik Kutra, Constantin Pape, and Erin Becker.
- Many community members have opened issues and pull requests to improve the lesson.

# Image Processing is stable!

Moved from "beta" to "stable" in January 2023.

![Four stages of lesson release timeline](https://cdh.carpentries.org/figures/release_timeline.svg)

# Why teach this lesson?

- Images are everywhere.
- Image data is different to tabular / data frame data.

# What's in the lesson?

- Introduction to images in research.
- How images are represented by computers.
- Software tools for working with images.
- Manipulating images using software.
- Extracting data / statistics from images.

# How do we think about image data?

![Magritte's "La Trahison des Images" ("The Treachery of Images") (1928-9) or "Ceci n'est pas une pipe" ("This is not a pipe").](https://upload.wikimedia.org/wikipedia/en/b/b9/MagrittePipe.jpg)

# Key concepts

- Pixels
- Arrays
- Coordinates
- Channels
- Kernels
- Binary masks

# What's not in the lesson?

- AI / Deep Learning

Lesson is a more "traditional" approach: easier to explain results, less data-intensive, applicable to more domains.

# What do I need to know?

- Bash shell skills
  - Navigating directories using `pwd`, `ls`, `cd <subdirectory>`, and `cd ..`, Run a Python script from the command line.
- Python skills
  - Variables and types, lists, logic (`if`, `else`, etc.), basic file input / output

# Lesson setup

- Data
  - Download from FigShare
- Software
  - Anaconda (base environment includes all required packages) and Jupyter Notebooks

# Introduction to image processing

- What research questions can we answer with image processing?
  - [imaging a Black Hole](https://iopscience.iop.org/article/10.3847/2041-8213/ab0e85)
  - [estimating the population of Emperor Penguins](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3325796/),
  - [the global-scale analysis of marine plankton diversity](https://www.cell.com/cell/fulltext/S0092-8674(19)31124-9),
  - [segmentation of liver and vessels from CT images](https://doi.org/10.1016/j.cmpb.2017.12.008)
- Morphometrics, also known as "measuring things in images".

# Optional breakout 1

- What research areas do you expect your learners to come from?
- Are there particular challenges in working with image data in these areas?

# Image basics

- Representation of images in computers.
- Images, arrays and pixels.
- How RGB is used to make colour images.
- File formats and compression.

# If you are a computer, images are arrays

<img src="https://datacarpentry.org/image-processing/fig/cat-corner-blue.png" alt="Image with pixel values overlaid" height="350"><br><p>Image with pixel values overlaid</p>

# Image representation

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard.png" alt="RGB Image"><br><p style="text-align:center">RGB Image</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-red-channel.png" alt="Red channel"><br><p style="text-align:center">Red channel</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-green-channel.png" alt="Green channel"><br><p style="text-align:center">Green channel</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-blue-channel.png" alt="Blue channel"><br><p style="text-align:center">Blue channel</p></td>
    </tr>
</table>

# Tools for working with images

- `skimage` (scikit-image)
  - Do weird things with arrays (e.g. `skimage.transform.resize`).
- `numpy`
  - Conventional array stuff (e.g. sub-setting, find all values `> x`).
- `imageio`
  - Input + output; images are often _not_ stored in `numpy` friendly formats.

# Analyzing images

The distribution of intensity of colour in an image can tell us things.

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/data/plant-seedling.jpg" alt="Plant Seedling" height="300"><br><p style="text-align:center">Plant Seedling</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/plant-seedling-colour-histogram.png" alt="Histogram" height="300"><br><p style="text-align:center">Histogram</p></td>
    </tr>
</table>

# Blurring

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/data/gaussian-original.png" alt="Gaussian Original" height="350"><br><p style="text-align:center">Original</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/gaussian-blurred.png" alt="Gaussian Blurred" height="350"><br><p style="text-align:center">Blurred</p></td>
    </tr>
</table>

# Thresholding

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-grayscale.png" alt="Blurred grayscale" height="350"><br><p style="text-align:center">Blurred grayscale</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-mask.png" alt="Threshold applied" height="350"><br><p style="text-align:center">Threshold applied</p></td>
    </tr>
</table>

# Connected components

Separating objects and getting information about them.

<img src="https://datacarpentry.org/image-processing/fig/shapes-01-labeled.png" alt="Labelled shapes" height="350"><br><p>Labelled shapes</p>

# Getting statistics

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-areas-histogram.png" alt="Areas histogram" height="350"><br><p style="text-align:center">Areas histogram</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-cca-detail.png" alt="False positive objects" height="350"><br><p style="text-align:center">False positive objects</p></td>
    </tr>
</table>

# Morphometrics

- Properties of the shape of an object.
- [skimage regionprops](https://scikit-image.org/docs/dev/api/skimage.measure.html#skimage.measure.regionprops)
- Basic e.g., area, perimeter, center
- More complex e.g., eccentricity, bounding box

# Capstone challenge

- Morphometrics for bacterial colonies.
- Brings together blurring, thresholding, and connected component analysis.

<img src="https://datacarpentry.org/image-processing/fig/colonies-01-summary.png" alt="Morphometrics for bacterial colonies" height="350">

# Optional breakout 2

- What imaging tools are people in your field using?
- How does that fit in with an open source image processing stack?

# Questions / discussion

# Thanks again!
