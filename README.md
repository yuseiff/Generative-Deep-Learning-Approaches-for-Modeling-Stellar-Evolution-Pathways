# Generative Deep Learning Approaches for Modeling Stellar Evolution Pathways

This project implements and compares Generative Adversarial Networks (GANs) and Variational Autoencoders (VAEs) for modeling stellar evolution using the HYG stellar database. The models learn to generate realistic Hertzsprung-Russell diagrams and simulate plausible stellar evolution tracks without explicit physical modeling.

*Standard theoretical HR diagram showing main regions: Main Sequence, Giants, Supergiants, and White Dwarfs*

## Dataset

We used the HYG Stellar Database (v4.2) containing 119,614 stellar entries. After preprocessing and filtering, we focused on these key features:

| mag | absmag | ci   | lum    | dist  | log_lum |
|-----|--------|------|--------|-------|---------|
| 5.86 | 5.86   | 0.418 | 1.05   | 10.32 | 0.021   |
| 4.95 | 4.95   | 0.580 | 1.52   | 10.32 | 0.182   |
| 5.08 | 5.08   | 0.467 | 1.16   | 10.32 | 0.064   |
| 5.35 | 5.35   | 0.388 | 0.93   | 10.32 | -0.032  |
| 4.66 | 4.66   | 0.329 | 1.71   | 10.32 | 0.233   |

*First 5 samples from the preprocessed HYG database*

## Models Trained

We trained and compared 6 different models with early stopping implemented in all cases:

1. **GAN-10e**: Generative Adversarial Network trained for 10 epochs
2. **GAN-100e (no callbacks)**: GAN trained for 100 epochs without advanced callbacks
3. **GAN-100e (with callbacks)**: GAN trained for 100 epochs with custom learning rate scheduling and early stopping
4. **VAE-200e**: Variational Autoencoder trained for 200 epochs
5. **VAE-300e**: Variational Autoencoder trained for 300 epochs  
6. **VAE-1000e**: Variational Autoencoder trained for 1000 epochs

## Results

### Real vs Synthetic HR Diagram Comparison

*Comparison of real stars (left) and GAN-generated synthetic stars (right) after 100 epochs with callbacks*

### Training History

*Training loss history for GAN showing discriminator and generator convergence*

### Stellar Evolution Tracks

*Generated stellar evolution tracks showing main sequence to red giant and white dwarf transitions*

## Project Structure
```
stellar-evolution-gan/
├── GANS_version.ipynb # GAN implementation notebook
├── VAE_version.ipynb # VAE implementation notebook
├── hyg_v42.csv # HYG stellar database
├── Results # included all the graphs and the results
└── README.md # This file
```

## License
The HYG database is licensed with the [Creative Commons Attribution-ShareAlike 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

