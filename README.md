# ComMark: A Query-Free, Integrity-Preserving Black-Box Attack Framework for Invisible Image Watermarking

We introduce ComMark, a query-free, integrity-preserving black-box attack framework targeting invisible image watermarking schemes designed to prevent generative AI misuse. ComMark uncovers a critical vulnerability: embedding watermarks in image latent representations makes these schemes susceptible to exploitation. Leveraging image compressive sensing techniques, ComMark sparsifies latent representations and reconstructs original images, effectively disrupting embedded watermarks while preserving image integrity
(encompassing both  quality and fidelity)
as measured by traditional metrics, all in a black-box, query-free manner without accessing watermarking schemes and detectors.

Our extensive evaluation on eight advanced invisible watermarking schemes demonstrates ComMark's superior effectiveness, reducing average watermark detection accuracy from 100% to 32.9% on average and surpassing state-of-the-art attack methods. Additionally, ComMark successfully compromises both post-processing and in-processing watermarking schemes without noticeably degrading image integrity. These findings indicate that current invisible watermarking approaches are insufficient for mitigating generative AI misuse, highlighting the need for ongoing research.

# Installations
- pytorch
- torchvision
- numpy
- timm
- transformers[torch]

# Datasets
- OpenImage: [OpenImage Dataset](https://docs.ultralytics.com/datasets/detect/open-images-v7/)
- COCO: [COCO Dataset](https://cocodataset.org/#home)

# Watermarking Schemes:
ComMark is evealuated against eight well-established watermarking schemes with their open-source implementation. 

- MBRS: MBRS employs a deep encoder-decoder architecture and enhances robustness by randomly applying random noise, simulated JPEG, or real JPEG during training, enabling it to effectively handle such distortions. [Open-source Implementation](https://github.com/jzyustc/MBRS)
- CIN: CIN improves watermark robustness against distortion while preserving invisibility. It uses an invertible network with diffusion, extraction, fusion, and split modules to enable symmetric watermark embedding and extraction. [Open-source Implementation](https://github.com/rmpku/CIN)
- Trustmark: TrustMark balances watermark invisibility and recovery accuracy using adversarial learning and spatio-spectral losses. It incorporates a noise module during training to simulate distortion and improve robustness. [Open-source Implementation](https://github.com/adobe/trustmark)
- PIMoG: PIMoG improves watermark robustness by integrating a noise layer during training to differentiably model distortion noises.[Open-source Implementation](https://github.com/FangHanNUS/PIMoG-An-Effective-Screen-shooting-Noise-Layer-Simulation-for-Deep-Learning-Based-Watermarking-Netw)
- VINEB: VINEB focuses on enhancing the watermark encoder. It uses a condition adaptor to encode images and watermarks into text sequences, which are then processed by the advanced text-to-image model SDXL-Turbo to generate watermarked images.[Open-source Implementation](https://github.com/Shilin-LU/VINE)
- VINER: VINER builds on VINEB by adding an adversarial learning module, similar to TrustMark and PIMoG. This module enhances the watermark extractor's ability to recover watermarks under diverse image distortions.[Open-source Implementation](https://github.com/Shilin-LU/VINE)
- StableSignature: StableSignature ensures all generated images embed a binary signature by fine-tuning the decoder of Latent Diffusion Models (LDM) with a pre-trained watermark encoder, decoder, and extractor.[Open-source Implementation](https://github.com/facebookresearch/stable_signature)
- PTW: PTW, a leading in-processing watermarking scheme for StyleGAN models, uses pivotal tuning to freeze the original model's parameters as a pivot while fine-tuning a secondary model with a watermark regularization term, enabling it to generate watermarked images.[Open-source Implementation](https://github.com/nilslukas/gan-watermark)
  
The final version of the source code, binaries and scripts for ComMark will be provided once the paper is accepted.
