# CTransformer Demo Repository 🎉

This repository provides an end-to-end demonstration of the CTransformer pipeline via Google Colab, along with the associated documentation and sample resources.

## 🎬 Video Tutorial & Walkthrough
Watch our step-by-step demonstration video on how to set up and run the `CellAtlasDemo.ipynb` pipeline:

https://youtu.be/kBr56B3mGE0

## 🔗 Useful Links & Downloads
- **Video Walkthrough**: [Watch on YouTube](https://youtu.be/kBr56B3mGE0)
- **Demo Dataset**: [Data Download (`CellAtlasDemo.zip`)](https://drive.google.com/file/d/1moNjHWOQANsEs6cbtywAS9mDxAxusjNh/view?usp=drive_link) *(Please upload this archive to your Google Drive --> My Drive root)*
- **Google Colab**: [Run the pipeline here](https://colab.research.google.com/drive/1USPG_FVm7-yMPB6kyvHvzxTv-pFucaxV?usp=sharing)
## 💻 Jupyter Notebook (.ipynb) Content Overview
The main demonstration notebook (`CellAtlasDemo.ipynb`) guides users through an end-to-end 3D bioimage informatics workflow:

- **Pipeline Workflow**: TIFF slices $\rightarrow$ 3D volumes (`.nii.gz format`) $\rightarrow$ PKL format $\rightarrow$ Membrane prediction $\rightarrow$ Instance cell segmentation $\rightarrow$ **m2nGAN** $\rightarrow$ Morphology $\rightarrow$ GUI.
- **Key Sections in the Notebook**:
  1. **Environment Setup & Drive Mounting**: Mounts Google Drive, extracts `CellAtlasDemo.zip`, and sets up an isolated Python 3.12 environment with pinned dependencies (`PyTorch`, `NumPy`, etc.) optimized for a **T4 GPU** runtime.
  2. **Lineage Dictionary Generation**: Checks the expected TIFF slices and time points, then generates numeric cell-label mappings from the lineage CSV files for downstream segmentation and visualization.
  3. **2D-to-3D Preprocessing**: Stacks 2D raw membrane and nucleus TIFF slices into 3D NIfTI (`.nii.gz`) volumes with calibrated voxel resolutions.
  4. **Pickle Conversion for Inference**: Converts the prepared NIfTI volumes into pickle files required by the model’s data-loading pipeline.
  5. **Membrane Prediction**: Loads a pretrained CTransformer checkpoint and predicts binary membrane volumes for the selected embryos.
  6. **Cell Instance Reconstruction**: Converts predicted membrane boundaries into labeled 3D cell instances, then combines regions associated with dividing cells to produce the volumes used by later analysis.
  7. **Pseudo-Nucleus Generation**: Runs the m2nGAN-based pseudo-nucleus stage and previews its outputs.
  8. **Morphological Feature Analysis**: Calculates per-cell volume, surface area, and cell-cell contact surface from the reconstructed instances. It then combines these measurements across time points and maps CD lineage coordinates into nucleus-location and morphology tables. 
  9. **Cell-Wise Visualization Data**: Packages labeled cell volumes, membrane images, statistics, and lineage-derived metadata into a GUI-ready directory, including per-time-point cell lists, lifespans, neighbors, divisions, and lost-cell records.
  10. **Tissue-Wise Visualization Data**: Maps cell-instance labels to cell-fate labels using CellFate.xls, then prepares a second GUI-ready dataset and its supporting metadata.
  11. **Quality Checks and Drive Export**: Runs final checks and copies both GUI datasets, morphology statistics, reports, and generated-nuclei outputs to CellAtlasDemoResults in Google Drive for inspection in ITK-CVE-SNAP.

## 🚀 How to Run
1. **Watch the Tutorial (Optional)**: Check the [Video Walkthrough](https://youtu.be/kBr56B3mGE0) for a complete visual guide.
2. **Prepare Data**: Upload `CellAtlasDemo.zip` to your Google Drive `My Drive`.
3. **Execute Notebook**: Open `CellAtlasDemo.ipynb` in Google Colab, select a **T4 GPU** runtime, and run the cells in order.
