# CTransformer Demo Repository 🎉

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing)

Welcome to the code examples, documentation, and resource hub for our coursework and demonstrations.

## 🎬 Video Tutorial & Walkthrough
Watch our step-by-step demonstration video on how to set up and run the `CellAtlasDemo.ipynb` pipeline:

https://youtu.be/kBr56B3mGE0

## 🔗 Useful Links & Downloads
- **Google Colab Notebook**: [Run `CellAtlasDemo.ipynb` in Colab](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing)
- **Video Walkthrough**: [Watch on YouTube](https://youtu.be/kBr56B3mGE0)
- **Demo Dataset**: [Data Download (`CellAtlasDemo.zip`)](https://drive.google.com/file/d/1moNjHWOQANsEs6cbtywAS9mDxAxusjNh/view?usp=drive_link) *(Please upload this archive to your Google Drive My Drive root)*

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
1. **Open in Colab**: Click the badge above or use the [Colab Link](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing) to open the notebook directly in your browser.
2. **Prepare Data**: Upload `CellAtlasDemo.zip` to your Google Drive `My Drive`. 
3. **Watch the Tutorial (Optional)**: Check the [Video Walkthrough](https://youtu.be/kBr56B3mGE0) for a complete visual guide.
4. **Execute Notebook**: Select a **T4 GPU** runtime in Colab and run the cells in order.
