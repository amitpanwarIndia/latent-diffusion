Latent Diffusion Model:

I have used repository (https://github.com/amitpanwarIndia/latent-diffusion) for my work on this Assignment, this is a fork repository of main repo (https://github.com/CompVis/latent-diffusion).
Orginal code have some obsolete package which I had to update in my own repo like pytorch_lightning.utilities.rank_zero etc.

I have also created fork repository for https://github.com/CompVis/taming-transformers as https://github.com/amitpanwarIndia/taming-transformers, because it also has some old unsupporte packages of torch in colab.

I have downloaded pretrained models as provided and ran sciprt and code to reproduce the results.


latent-diffusion repositoy code workflow:

Various scripts are provided under sciprts folder to perform different tasks like scripts/txt2img.py to generate image from text prompt basis on configuration, similarly for inpaiting work we can use scripts/inpaint.py

Different checkpoint of pre trained models are provided which are then used with predefined configuration setup for specific task under configs folder in form yaml files. Models are saved under models/ldm directory. For conditioning image synthesis data directory has been provided for sample and example for image synthesis.

Output fir samples are stored under default directory outputs/

ldm directory contains all code for loading models based on configuration and then synthesizing the images.

Autoencoders can also be trained using main.py with different type of datasets but requires very high GPU power and similarly for latent diffusion models.

I have used a basic scipr to generate images as shown in Jupyter file https://github.com/amitpanwarIndia/latent-diffusion/blob/main/AML_Assignment_03_0_2.ipynb, I also tried with sciprts/txt2img.py to generate images based on prompt. And then finally generated unconditional images.

Downloaded pretrained model using:

mkdir -p models/ldm/text2img-large/
wget -O models/ldm/text2img-large/model.ckpt https://ommer-lab.com/files/latent-diffusion/nitro/txt2img-f8-large/model.ckpt

and sampled with 
python scripts/txt2img.py --prompt "a virus monster is playing guitar, oil on canvas" --ddim_eta 0.0 --n_samples 4 --n_iter 4 --scale 5.0  --ddim_steps 50


Final synthesis was done as script for class conditoning is shown in Jupyter notebook.
