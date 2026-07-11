# Conditional Latent Diffusion for Attribute Editing

This project studies conditional latent diffusion as a method for semantic face editing. Rather than operating directly in pixel space, the approach works in the latent space of a StyleGAN generator, where edits can be guided by a chosen attribute. Gender is used as a concrete example, but the same framework can be extended to other attributes supported by a classifier.

## Project overview
The work examines how a diffusion-based editing procedure can steer a source face toward a target semantic attribute while preserving as much identity information as possible. The project focuses on the interaction between noise strength, guidance scale, and edit quality.

## Main artifacts
- `reports/conditional-latent-diffusion-report.pdf` — the main project report
- `notebooks/stylegan2-latent-diffusion-editing.ipynb` — the latent diffusion editing workflow
- `notebooks/celeba-gender-classifier.ipynb` — a supporting classifier notebook used to define the target attribute

## Method
1. Generate latent vectors from a StyleGAN generator.
2. Use a classifier to assign a score to a chosen semantic attribute.
3. Train a latent diffusion model conditioned on that attribute label.
4. Apply SDE-Edit to progressively denoise a latent representation toward the desired attribute.
5. Evaluate how the edit changes the image under different settings.

## Key observations
- Lower noise levels tend to preserve identity more faithfully, but produce weaker edits.
- Higher noise levels make the attribute change more visible, but can also distort identity.
- Stronger guidance increases the influence of the target attribute, though it may reduce realism.
- The method is broader than the gender example: the same pipeline can be applied to other semantic attributes available in the dataset.

## Repository structure
- `reports/` — report files and supporting documentation
- `notebooks/` — experiment and analysis notebooks
