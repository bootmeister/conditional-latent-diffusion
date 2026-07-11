# Conditional Latent Diffusion for Gender Editing

This project explores conditional latent diffusion for face editing using StyleGAN latent representations. The main goal is to transform a source face toward a target gender attribute while studying the trade-off between identity preservation and attribute change.

## Project focus
The work is centered on a diffusion-based editing method applied in the latent space of StyleGAN rather than directly in pixel space. The project investigates how different noise levels and guidance scales affect the quality of the generated edits.

## Main artifacts
- `reports/conditional-latent-diffusion-report.pdf` — the main project report
- `notebooks/stylegan2-latent-diffusion-editing.ipynb` — the latent diffusion editing workflow
- `notebooks/celeba-gender-classifier.ipynb` — a supporting gender-classifier notebook

## Summary of the method
1. Generate StyleGAN latent vectors from random samples.
2. Use a pretrained gender classifier to label generated faces.
3. Train a latent diffusion model conditioned on the target label.
4. Apply SDE-Edit to progressively denoise a noisy latent vector toward the target attribute.
5. Analyze how noise strength and guidance affect the final edited image.

## Key findings
- Low noise preserves identity better but produces weaker gender changes.
- Higher noise makes the gender edit stronger but can distort identity.
- Stronger guidance increases the prominence of the target attribute, but may also reduce realism.

## Repository structure
- `reports/` — project report files
- `notebooks/` — analysis and experiment notebooks
