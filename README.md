# ELIXIR + DEXTER
This is the home of *Enhancing Long-range Images for X-ray Inspection via Reconstruction* (**ELIXIR**) method and *DEgraded X-ray image Tomography, Enhancement, and Reconstruction* (**DEXTER**) dataset. Both are introduced in our VISION'26 paper *Dataset and Baseline Method for Long-range X-ray Image Enhancement, 3D Reconstruction, and Object Recognition*.

## DEXTER
Dataset consists of 650 scenes. Each scene is in a separate directory, named using date and time of its generation. The wooden crate in each scene is randomly filled with 8 to 27 objects. The objects are randomly sampled from [ModelNet40](https://github.com/lmb-freiburg/orion).

We provide 3D reconstructions and enhanced views of `blurred` set in subdirectory `tv2_0.03_tv3_0.001_bsz3_usi_intnn_1_blur_11_l2_av_renorm`. 3D images are in two formats: NumPy (.npz)  and VTK XML ImageData (.vti). Neither contains physical spacing information. They can be aligned with proper physical space of ground truth (3D meshes and .nrrd format 3D images) using a rigid transform in ITK format (.tfm). A convenient program to visualize everything is [3D Slicer](https://www.slicer.org/).

Majority of the source code of dataset generator is in `simulator` directory. We used `modelnet40_manually_aligned` as input to `ConvertOFF2STL.py`, in order to generate the centered meshes which are used by `main.py`.

## ELIXIR
The baseline reconstruction method is provided in `reconstruction_nerf` directory.

## Running the code

Create a Python 3.10 virtual environment using your favorite method, then activate it
and install the required packages: `pip install -r requirements.txt`
