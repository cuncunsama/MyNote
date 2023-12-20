## DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation (CVPR2023)
*<https://ieeexplore.ieee.org/document/10204880/authors#authors>*  
*<https://dreambooth.github.io>* 

**Problem**  
Large text-to-text models cannot mimic the appearance of subjects in a given reference set and synthesize novel renditions of them in different contexts.  

The diffusion models slowly forgets how to generate subjects of the same class as the target subject.  

Text-to-image diffusion models naturally posses high amounts of output diversity. There is a risk of reducing the amount of variability in the output poses and views of the subject when fine-tuning on a small set of images.

*language drift*  

**Effect** The effect is akin to a “magic photo booth”—once a few images of the subject are taken, the booth generates photos of the subject in different conditions and scenes, as guided by simple and intuitive text prompts.

## Learning Transferable Visual Models From Natural Language Supervision(CLIP)
*<https://openai.com/research/clip>*  
*<https://arxiv.org/abs/2103.00020>*  
*<https://github.com/openai/CLIP>*  

**CLIP(Contrastive Language-Image Pre-training)**  
CLIP (Contrastive Language–Image Pre-training) builds on a large body of work on zero-shot transfer, natural language supervision, and multimodal learning.
CLIP **was designed to** mitigate a number of major **problems** in the standard deep learning approach to computer vision:  
**1. Costly datasets**  

**2. Narrow**  
**3. Poor real-world performance**  
There is a gap between "benchmark performance" and "real performance". The author conjecture that this gap occurs because the models "cheat" by only optimizing for performance on the benchmark, much like a student who passed an exam by studying only the questions on past years' exams. In contrast, the clip model can be evaluated on benchmarks without having to train on their data, so it can't "cheat" in this manners.















