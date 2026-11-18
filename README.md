# CTransformer Demo Repository

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing)

This repository provides the official code demonstration, documentation, and supplementary resources for **CTransformer**, prepared to facilitate reproducibility and evaluation during peer review.

## Video Walkthrough
A step-by-step demonstration video detailing the setup and execution of the `CellAtlasDemo.ipynb` pipeline is available at:

- **YouTube**: [Watch the Video Walkthrough](https://youtu.be/kBr56B3mGE0)

## Resources & Links
- **Interactive Notebook**: [Open `CellAtlasDemo.ipynb` in Google Colab](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing)
- **Demonstration Video**: [Watch on YouTube](https://youtu.be/kBr56B3mGE0)
- **Sample Dataset**: [Download `CellAtlasDemo.zip`](https://drive.google.com/file/d/1moNjHWOQANsEs6cbtywAS9mDxAxusjNh/view?usp=drive_link) *(Please upload this archive to the root directory of your Google Drive `My Drive`)*

## Notebook Overview (`CellAtlasDemo.ipynb`)
The main demonstration notebook guides users through an end-to-end 3D bioimage informatics pipeline:

- **Processing Workflow**: TIFF slices $\rightarrow$ 3D volumes (`.nii.gz`) $\rightarrow$ PKL format $\rightarrow$ Membrane prediction $\rightarrow$ Instance cell segmentation $\rightarrow$ **m2nGAN** $\rightarrow$ Morphology analysis $\rightarrow$ GUI visualization.
- **Pipeline Modules**:
  1. **Environment Setup & Drive Mounting**: Mounts Google Drive, extracts `CellAtlasDemo.zip`, and configures an isolated Python 3.12 environment with pinned dependencies (`PyTorch`, `NumPy`, etc.) optimized for a **T4 GPU** runtime.
  2. **Lineage Dictionary Generation**: Generates `name_dictionary.csv` and `number_dictionary.csv` from embryonic cell lineage tracking files.
  3. **3D Volume Composition**: Stacks 2D raw membrane and nucleus TIFF slices into 3D NIfTI (`.nii.gz`) volumes with calibrated voxel resolutions.
  4. **Nuclear Segmentation (SegNuc)**: Constructs nuclear location segmentations based on CD lineage files (`CDFiles/*.csv`).
  5. **Volume Inspection**: Utilizes `Matplotlib` and `Nibabel` to visualize mid-plane horizontal (XY), sagittal (YZ), and coronal (XZ) slices of the processed 3D embryonic volumes.

## Instructions for Execution
1. **Launch the Notebook**: Click the **Open in Colab** badge above or follow the [Google Colab Link](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing) to open the notebook in your browser.
2. **Prepare the Dataset**: Download `CellAtlasDemo.zip` and upload it directly to the root directory of your Google Drive (`My Drive`).
3. **Configure Runtime**: In Google Colab, navigate to `Runtime` $\rightarrow$ `Change runtime type` and select a **T4 GPU** hardware accelerator.
4. **Run the Pipeline**: Execute the notebook cells sequentially from top to bottom. For visual guidance, please refer to the [Video Walkthrough](https://youtu.be/kBr56B3mGE0).
