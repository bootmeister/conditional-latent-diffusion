# Conditional Latent Diffusion for Attribute Editing

This project explores conditional latent diffusion for face editing using StyleGAN latent representations. The gender attribute is used as a concrete example of a semantic attribute to edit, but the approach is not limited to gender. In principle, any attribute available in the dataset and represented by a trainable classifier could be used instead.

## Project focus
The work is centered on a diffusion-based editing method applied in the latent space of StyleGAN rather than directly in pixel space. The project investigates how different noise levels and guidance scales affect the quality of the generated edits, and it illustrates a general framework for semantic attribute editing.

## Main artifacts
- `reports/conditional-latent-diffusion-report.pdf` — the main project report
- `notebooks/stylegan2-latent-diffusion-editing.ipynb` — the latent diffusion editing workflow
- `notebooks/celeba-gender-classifier.ipynb` — a supporting classifier notebook used to define the target attribute

## Summary of the method
1. Generate StyleGAN latent vectors from random samples.
2. Use a classifier to label generated faces with a chosen semantic attribute.
3. Train a latent diffusion model conditioned on the target label.
4. Apply SDE-Edit to progressively denoise a noisy latent vector toward the target attribute.
5. Analyze how noise strength and guidance affect the final edited image.

## Key findings
- Low noise preserves identity better but produces weaker attribute changes.
- Higher noise makes the target edit stronger but can distort identity.
- Stronger guidance increases the prominence of the chosen attribute, but may also reduce realism.
- The method is general: the gender example is arbitrary, and the same framework could be applied to other attributes available in the dataset.

## Repository structure
- `reports/` — project report files
- `notebooks/` — analysis and experiment notebooks
