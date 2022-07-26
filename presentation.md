% Instructor Onboarding for Data Carpentry: Image Processing with Python (beta)
% Robert Turner, "Image Processing with Python" maintainers
% August, 2022

<style>
    .reveal h1 { font-size: 2em; }
    .reveal h2 { font-size: 1.5em; }
</style>

<script>
Reveal.initialize({ slideNumber: true });
</script>

# Thank you!

Thanks to CarpentryCon 2022 for having this session, thank you for coming.

# Presenters

- Robert "Bob" Turner
- Toby Hodges
- David Palmquist

# What is a "beta" lesson?

Pre-alpha-->Alpha-->**Beta**-->Stable

- Exercise caution
- Feedback welcome
- Second beta pilot needed (please get in touch)

# Why teach this lesson?

- Images are everywhere.
- Images data is different to data frame data.

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

Lesson is a more "traditional" approach: easier to explain results, less data-intensive.

# [What do I need to know first?](https://datacarpentry.org/image-processing/prereqs/index.html)

- Bash shell skills
  - Navigating directories using `pwd`, `ls`, `cd <subdirectory>`, and `cd ..`, Run a Python script from the command line.
- Python skills
  - Variables and types, lists, logic (`if`, `else`, etc.), basic file input / output

# [Setup](https://datacarpentry.org/image-processing/setup/)

- Data
  - Download from FigShare
- Software
  - Anaconda (base environment includes all required packages) and Jupyter Notebooks

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

# If you are a computer, images are arrays

<img src="https://datacarpentry.org/image-processing/fig/cat-corner-blue.png" alt="Image with pixel values overlaid" height="250"><br><p>Image with pixel values overlaid</p>

# Image Representation

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard.png" alt="RGB Image"><br><p>RGB Image</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-red-channel.png" alt="Red channel"><br><p>Red channel</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-green-channel.png" alt="Green channel"><br><p>Green channel</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/checkerboard-blue-channel.png" alt="Blue channel"><br><p>Blue channel</p></td>
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
        <td><img src="https://datacarpentry.org/image-processing/data/plant-seedling.jpg" alt="Plant Seedling" height="250"><br><p>Plant Seedling</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/plant-seedling-colour-histogram.png" alt="Histogram" height="250"><br><p>Histogram</p></td>
    </tr>
</table>

# [Ep. 6 Blurring Images](https://datacarpentry.org/image-processing/06-blurring/index.html)

- Why blur?
- What's the relationship between blurring, filtering, convolution and kernels?

# Effects of blurring

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/data/gaussian-original.png" alt="Gaussian Original" height="250"><br><p>Not Blurred</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/gaussian-blurred.png" alt="Gaussian Blurred" height="250"><br><p>Blurred</p></td>
    </tr>
</table>

# [Ep. 7 Thresholding](https://datacarpentry.org/image-processing/07-thresholding/index.html)

- What is thresholding?
- Why would we want to do it?
- What methods are available?

# "Simple" Thresholding

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-grayscale.png" alt="Blurred Grayscale" height="250"><br><p>Blurred Grayscale</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-mask.png" alt="Threshold Applied" height="250"><br><p>Threshold Applied</p></td>
    </tr>
</table>

# [Ep 8. Connected Components](https://datacarpentry.org/image-processing/08-connected-components/index.html)

- Separating objects and getting information about them.

<img src="https://datacarpentry.org/image-processing/fig/shapes-01-labeled.png" alt="Labelled Shapes" height="250"><br><p>Labelled Shapes</p>

# Getting statistics

<table>
    <tr>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-areas-histogram.png" alt="Areas Histogram" height="250"><br><p>Areas Histogram</p></td>
        <td><img src="https://datacarpentry.org/image-processing/fig/shapes-01-cca-detail.png" alt="False Positive Objects" height="250"><br><p>False Positive Objects</p></td>
    </tr>
</table>

# Morphometrics

- Properties of the shape of an object.
- [skimage regionprops](https://scikit-image.org/docs/dev/api/skimage.measure.html#skimage.measure.regionprops)
- Basic e.g. area, perimeter, center
- More complex e.g. eccentricity, bounding box

# [Ep 9. Capstone Challenge](https://datacarpentry.org/image-processing/09-challenges/index.html)

- Brings together blurring, thresholding and connected component analysis.
- Example used is counting colonies of bacteria.

# Questions / discussion

# Thanks again!
