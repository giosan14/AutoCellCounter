# Cell Counting Algorithm for Hemocytometer and Histological Cuts

## Summary

At the end of the 19th century, a technique was first created to count blood cells, which is performed using a hemocytometer made of special optical glass. This process involves placing cellular suspensions in specific quantities on the hemocytometer, followed by a cell count under the microscope, which is an estimate since there may be more or fewer cells. While this process is cost-effective, it has multiple disadvantages, including errors in identification due to irregular sample distribution, contamination of the hemocytometer, subjective interpretations of counted areas, and overall differences in technique among specialists. Additionally, it is a time-consuming and tedious process for specialists.

Cell counting is crucial for cell culture or subculture, as it is used for cell-based experiments, and it is essential to mention that cell counts can monitor the health and proliferation levels of cultures. Therefore, cell counts must be precise and rapid.

In addition to this technique for cell counting in cell suspensions, other techniques are used to analyze tissue pieces extracted from biopsies, called histological cuts. This involves a thin section of biological tissue attached to a slide and colored by a specific stain for visualization of the structures of the slice.

The present report proposes an algorithm for automatic recognition and quantification based on cellular shape to achieve optimal counting of cellular figures in histological cuts. This algorithm offers the advantage of obtaining the cell count more quickly, reducing response times for disease diagnosis. Since it is crucial to have an accurate count for an accurate diagnosis of various conditions, this problem is addressed to generate the count. It is important to note that this is a support for specialists, not a substitute for them, focusing efforts and saved time on the treatment of individuals, thereby reducing the workload for specialists.

## Neubauer Hemocytometry Technique

The Neubauer chamber counting consists of placing the sample on the slide and filling two small spaces on it. These spaces are called "chambers" and contain a counting grid that divides into 9 zones with a square shape, each measuring 3 mm on each side. The areas marked with an "L" correspond to 1 square millimeter.

If we count the four shaded areas (L or A, B, C, and D), observing a total of N cells among the four areas, the cellular concentration in the cell suspension is given by the following formula:
Concentration of suspension = N * 10^4 * dil

If the cells are counted in the central square, considering only the 5 smaller squares within the central square marked with X, the cell concentration is calculated according to the following formula:
Concentration of suspension = √((N/4) / 10^(-6)) * dil

## Implementation of Cell Counting Model

The diagram in Figure 2 illustrates the modules and stages used to obtain an approximate cell count. The code development (included in the project) explains descriptively why the code was used.

1. Image reading
2. Conversion of image to grayscale
3. Image enhancement
4. Image smoothing
5. Image thresholding
6. Morphological filters
7. Image opening
8. Noise reduction
9. Result output
   - Counting of resulting regions
   - Generation of processed image

## Results

Based on this process, the resulting images and their cell counts are displayed, along with a comparison of cell counts performed by a specialist.

Specialist count: 950 - 1000 cells
Algorithm count: 1055 cells

Specialist count: 700 - 750 cells
Algorithm count: 687 cells

Specialist count: 950 - 1000 cells
Algorithm count: 1031 cells

## Conclusions

In comparison with the results given by a specialist, the result obtained by the algorithm is extremely close to the count performed. Like the counts by specialists, there is a small variation in cell estimation, and applying this variation to the result obtained by the algorithm, it is concluded that it functions optimally and similarly to specialists.
