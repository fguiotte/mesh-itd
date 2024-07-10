# Mesh individual tree detection and segmentation

Efficient individual tree detection (ITD) and segmentation method for LiDAR point clouds.

## Installation

```sh
git clone https://github.com/fguiotte/mesh-itd.git
cd mesh-itd
conda env create -f environment.yml
conda activate mesh-itd-seg
./mesh-itd-seg.py <
mesh-itd-seg.py [-h] input_pc output_pc
```

## Usage

```sh
mesh-itd-seg.py input.las output.ply
```

You can use point cloud formats such as LAS and PLY as input, but only PLY is supported as the output format for now.

## Notes

- The `mesh-itd-seg` script reads an unlabelled raw point cloud, detects and segments the point cloud into trees, and assigns tree IDs in the "ClusterID" field.
- Tree IDs range from 1 to the total number of detected trees, with 0 representing a non-tree point.
- If a ground label is present in the input point cloud, it will be used as a mask for the tree IDs.
- The process may exclude specific points from the raw input if they cannot be included in the Delaunay mesh.

## Citation

If you find this repository helpful in your research or work, please consider citing the following paper:

```bib
@inproceedings{GuiotteMesh2024,
  title = {Mesh Surface and Morphological Hierarchies for Individual Tree Detection and Segmentation from {{LiDAR}} Data},
  booktitle = {{{IEEE}} International Geosciences and Remote Sensing Symposium},
  author = {Guiotte, Florent and Kostensalo, Joel and Laaksonen, Jorma},
  year = {2024},
  address = {Athens, Greece},
}
```
