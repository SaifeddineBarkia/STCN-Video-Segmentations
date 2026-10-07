# Video Object Segmentation with STCN

> MVA (ENS Paris-Saclay) · Object Recognition & Computer Vision (2021)
> **Team:** **Saifeddine Barkia**, Hamza Meddeb

Study, reproduction and extension of **STCN** (*Rethinking Space-Time Networks with Improved Memory Coverage*, Cheng et al., NeurIPS 2021) for semi-supervised video object segmentation: given the object's mask in the first frame, segment it in every following frame.

## What we did

1. **STCN vs STM:** analysed how STCN computes a single frame-to-frame affinity from RGB-only key encoders, instead of one per object. This makes it more efficient and robust than STM.
2. **Reproduced the authors' results** on **DAVIS 2016** and **DAVIS 2017**.
3. **Automated the first-frame mask:** replaced the ground-truth mask with predictions from **Mask R-CNN** and **Swin Transformer**. Swin masks reached a Jaccard index of about 0.94–0.97 against the ground truth on the frames we tested.
4. **Generalisation test** on the **Something-Something** dataset, including converting bounding boxes to masks.

## Findings

- STCN is robust to an imperfect initial mask and can even turn a bounding box into a good mask.
- Only the first frame needs a heavy segmentation model; STCN propagates it efficiently afterwards.
- **Limitation:** it can't segment objects that appear after the first frame.

📄 [Report](./FPR_BARKIA_MEDDEB.pdf) · 📊 [Slides](./Presentation.pptx)

**Stack:** PyTorch · Mask R-CNN · Swin Transformer · DAVIS
