### Learning Transferable Visual Models From Natural Language Supervision
**CLIP-ICML2021**
*<https://openai.com/research/clip>*  
*<https://arxiv.org/abs/2103.00020>*  
*<https://github.com/openai/CLIP>*  

**CLIP(Contrastive Language-Image Pre-training)**  

CLIP (Contrastive Language–Image Pre-training) builds on a large body of work on zero-shot transfer, natural language supervision, and multimodal learning.
CLIP **was designed to** mitigate a number of major **problems** in the standard deep learning approach to computer vision:  

**1. Costly datasets**  

**2. Narrow**  
An ImageNet model is good at predicting the 1000 ImageNet categories, but that's all it can do "out of the box". To apply CLIP to a new task, all we need to do is "tell" CLIP's text-encoder the names of the task's visual concepts, and it will output a linear classifier of CLIP's visual representations. The accuracy of this classifier is often competitive with fully supervised models.  

**3. Poor real-world performance**  
There is a gap between "benchmark performance" and "real performance". The author conjecture that this gap occurs because the models "cheat" by only optimizing for performance on the benchmark, much like a student who passed an exam by studying only the questions on past years' exams. In contrast, the clip model can be evaluated on benchmarks without having to train on their data, so it can't "cheat" in this manners.  

# CVPR-2023
### 《DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation》(CVPR2023)
*<https://ieeexplore.ieee.org/document/10204880/authors#authors>*  
*<https://dreambooth.github.io>* 

**Problem**  
Large text-to-text models cannot mimic the appearance of subjects in a given reference set and synthesize novel renditions of them in different contexts.  

The diffusion models slowly forgets how to generate subjects of the same class as the target subject.  

Text-to-image diffusion models naturally posses high amounts of output diversity. There is a risk of reducing the amount of variability in the output poses and views of the subject when fine-tuning on a small set of images.

*language drift*  

**Effect** The effect is akin to a “magic photo booth”—once a few images of the subject are taken, the booth generates photos of the subject in different conditions and scenes, as guided by simple and intuitive text prompts.

## 《Run, Don't Walk: Chasing Higher FLOPS for Faster Neural Networks》
Paper: *<https://ieeexplore.ieee.org/document/10203371>*  
Code: *<https://github.com/JierunChen/FasterNet>*
### FasterNet
```
cd ~/Codebase/FasterNet
conda activate fasternet
```
**Evaluation**
```
python train_test.py -c cfg/fasternet_t0.yaml \
--checkpoint_path model_ckpt/fasternet_t0-epoch=281-val_acc1=71.9180.pth \
--data_dir ~/Data/datasets/imagenNet-1k --test_phase -g 1 -e 125
```
## 《ConvNeXt V2: Co-designing and Scaling ConvNets with Masked Autoencoders》
Paper: *<https://ieeexplore.ieee.org/document/10205236>*  
Code: *<https://github.com/facebookresearch/ConvNeXt-V2>*


## 《Scaling up GANs for Text-to-Image Synthesis》
Paper: *<[url](https://ieeexplore.ieee.org/document/10205294/references#references)>*  
Code: *<url>*

## 《Imagic: Text-Based Real Image Editing with Diffusion Models》
Paper: *<[url](https://ieeexplore.ieee.org/document/10203581)>*  
Code: *<url>*  
Method: Imagic  
Input: A single input image and a target text(the desired edit)  
Eg: Making a standing dog sit down, cause a bird to spreads its wings, etc.

## 《GALIP: Generative Adversarial CLIPs for Text-to-Image Synthesis》
Paper: *<[url](https://ieeexplore.ieee.org/document/10203358)>*  
Code: *<[url](https://github.com/tobran/GALIP)>*  
#### DALL-E and LDM
DALL-E and LDM show impressive ability to synthesize complex scenes and outperform the previous GAMs. They still suffer from three flaws.  
1. Require tremendous training data and parameters for pretraining.
2. The generation of large models is much slower than GANs.
GAN's strength: GANs are much faster than autoregressive and diffusions models and have smooth latent space, which enables more controllable sythesis. The token-by-token generation and progressive denoising require hundreds of inference steps and make the generated results lag the language inputs seriously.  
3. There is no intuitive smooth latent space as GANs, which maps meaningful visual attributes to the latent vector.
#### GAN
**Weakness**: Potentially unstable training and less diversity in the generation.  
**Introduce the pretrained CLIP into text-to-image GANS**  

## 《GLIGEN: Open-Set Grounded Text-to-Image Generation》
Paper: *<[url](https://ieeexplore.ieee.org/document/10203593)>*  
Code: *<url>*  
**GROUNED TEXT2IMAG GENERATION WITH BOUNDING BOXES**
**Question1**
The existing large-scale text-to-image generation models **cannot be conditioned on other modalities apart from text**, and cannot thus precisely localize concepts.  
**combine those inputs**  
**Question2**  
*Can we build upon existing pretrained diffusion models and endow them with new conditional input modalities?*  
**Challenge**
The Key challenge is preserving the original vast concept knowledge in the pretrained model while learning to inject the new grounding information.
**Fix**: Freeze the original model weights and add new trainable gated Transformer layers.  
**Gated mechanism**

## 《Diffusion Probabilistic Model Made Slim》
Paper: *<https://ieeexplore.ieee.org/document/10204618>*  
diffusion probabilitic models(DPMs)  
This paper makes a dedicated attempt to lighten DPM while striving to preserve its favourable performance.  
**Lighten the model**  
DALL-E2 is one of DPMs  
DALL-E2 is composed of 4 separate diffusion models, requirese 5.5B parameters and 356 sampling steps in total.  
The primary obstacle to training small DPMs is their inability to provide high-frequency realistically, which results from the frequency evolution and bias of diffusion process. In order to resolve these problems, we propose Spectral Diffusion (SD) for efficient image generation. It performs spectrum dynamic denoising by using a wavelet gating operation, which automatically enhances different frequency bands at different reverse steps.  


## Paper template
Paper: *<url>*  
Code: *<url>*

## Paper template
Paper: *<url>*  
Code: *<url>*






# Stability-AI
### stable-webui
```
conda activate sdwebui
cd ~/Codebase/stable-diffusion-webui
./webui.sh
```
### generative-models
```
cd generative-models/
source .pt2/bin/activate
PYTHONPATH=$PWD streamlit run scripts/demo/sampling.py --server.port 7860

```
- Put weights in /checkpoints/

# Google AI
## 2019《 BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding 》
*<https://arxiv.org/abs/1810.04805>*  
*<https://github.com/google-research/bert>*  


# Arxiv
### 《Discovering the Hidden Vocabulary of DALLE-2》
*<extension://bfdogplmndidlpjfhoijckpakkdjkkil/pdf/viewer.html?file=https%3A%2F%2Farxiv.org%2Fpdf%2F2206.00169.pdf>*  
DALLE-2 have a hidden vocabulary  

### DALLE2《Hierarchical Text-Conditional Image Generation with CLIP Latents》
Paper: *<(https://ar5iv.labs.arxiv.org/html/2204.06125?_immersive_translate_auto_translate=0)>*  
Code: *<url>*  
Two-stage model: a prior that generates an image embedding given a text caption, and a decoder that generates an image conditioned on the image embedding.  
prior: diffusion model yes autoregressive no  
decoder: diffusion model  















