# CTransformer Demo Repository 🎉

Welcome to the code examples, documentation, and resource hub for our coursework and demonstrations.

## 🔗 Useful Links & Downloads
- [Data Download (`CellAtlasDemo.zip`)](https://drive.google.com/file/d/1VyZy4QkksD8jkhTH5Fk-nLAVuTaXg-x3/view?usp=sharing) *(Please upload this archive to your Google Drive My Drive root)*
- [Official Course Website](https://example.com)
- [Python Official Documentation](https://www.python.org)

## 💻 Jupyter Notebook (.ipynb) Content Overview
The main demonstration notebook (`CellAtlasDemo.ipynb`) guides users through an end-to-end 3D bioimage informatics workflow:

- **Pipeline Workflow**: TIFF slices $\rightarrow$ 3D volumes (`.nii.gz format`) $\rightarrow$ PKL format $\rightarrow$ Membrane prediction $\rightarrow$ Instance cell segmentation $\rightarrow$ **m2nGAN** $\rightarrow$ Morphology $\rightarrow$ GUI.
- **Key Sections in the Notebook**:
  1. **Environment Setup & Drive Mounting**: Mounts Google Drive, extracts `CellAtlasDemo.zip`, and sets up an isolated Python 3.12 environment with pinned dependencies (`PyTorch`, `NumPy`, etc.) optimized for a **T4 GPU** runtime.
  2. **Lineage Dictionary Generation**: Generates `name_dictionary.csv` and `number_dictionary.csv` for embryonic cell lineage tracking files.
  3. **3D Volume Composition**: Stacks 2D raw membrane and nucleus TIFF slices into 3D NIfTI (`.nii.gz`) volumes with calibrated voxel resolutions.
  4. **Nuclear Segmentation (SegNuc)**: Constructs nuclear location segmentations based on CD lineage files (`CDFiles/*.csv`).
  5. **Volume Inspection**: Utilizes Matplotlib and Nibabel to visualize middle horizontal (XY), sagittal (YZ), and coronal (XZ) slices of the processed 3D embryonic volumes.

## 🚀 How to Run
1. Upload `CellAtlasDemo.zip` to your Google Drive `My Drive`.
2. Open the notebook in Google Colab, select a **T4 GPU** runtime, and run the cells in order.
