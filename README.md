<div align="center">
    <img src="./assets/LOGO.png" width="280px"></img>
</div>
<div align="center">
    <img src="./assets/Typing_re.gif" width="320px"></img>
</div>

<div align="center">
<h2>PixelHacker: Image Inpainting with Structural and Semantic Consistency</h2>

**_SOTA performance on Places2, CelebA-HQ, and FFHQ & Superior structural and semantic consistency_**

[Ziyang Xu](https://ziyangxu.top)<sup>1</sup>, [Kangsheng Duan](https://github.com/AnduinD)<sup>1</sup>, Xiaolei Shen<sup>2</sup>, Zhifeng Ding<sup>2</sup>, [Wenyu Liu](http://eic.hust.edu.cn/professor/liuwenyu)<sup>1</sup>, Xiaohu Ruan<sup>2</sup>,  
[Xiaoxin Chen](https://scholar.google.com/citations?hl=zh-CN&user=SI_oBwsAAAAJ)<sup>2</sup>, [Xinggang Wang](https://xwcv.github.io)<sup>1 :email:</sup>

(<sup>:email:</sup>) Corresponding Author.

<sup>1</sup> Huazhong University of Science and Technology. <sup>2</sup> VIVO AI Lab.  

[![arxiv](https://img.shields.io/badge/arXiv'25-Paper-orange)](https://arxiv.org/abs/2504.20438) [![license](https://img.shields.io/badge/License-Apache_2.0-blue)](LICENSE) [![Project](https://img.shields.io/badge/Project_Page-https://hustvl.github.io/PixelHacker-purple)](https://hustvl.github.io/PixelHacker)
</div>

<img src="./assets/Pipeline.png"></img>

## 🌟 Highlights
* **Latent Categories Guidance (LCG)**: Simple yet effective inpainting paradigm with superior structural and semantic consistency. Let's advance inpainting research to challenge more complex scenarios!
* **PixelHacker**: Diffusion-based inpainting model trained with LCG, outperforming SOTA performance across multiple natural-scene (Places2) and portrait (CelebA-HQ, and FFHQ) benchmarks!
* **Comprehensive SOTA Performance**：
    * **Places2** (Natural Scene)
        * Evaluated at 512 resolution using 10k test set images with 40-50% masked regions, PixelHacker achieved the best performance with **FID 8.59** and **LPIPS 0.2026**.
        * Evaluated at 512 resolution using 36.5k validation set images with large and small mask settings, PixelHacker achieved the best performance on **FID (large: 2.05, small: 0.82)** and **U-IDS (large:36.07, small:42.21)**, and the second best performance on **LPIPS (large:0.169, small:0.088)**.
        * Evaluated at 256 and 512 resolutions using validation set images with a highly randomised masking strategy, PixelHacker achieved the best performance at 512 resolution with **FID 5.75 and LPIPS 0.305**, and the second best performance at 256 resolution with **FID 9.25 and LPIPS 0.367**.
    * **CelebA-HQ** (Portrait Scene)
        * Evaluated at 512 resolution, PixelHacker achieved the best performance with **FID 4.75 and LPIPS 0.115**.
    * **FFHQ** (Portrait Scene)
        * Evaluated at 256 resolution, PixelHacker achieved the best performance with **FID 6.35 and LPIPS 0.229**.

## 🔥 News

* **`June 18, 2026`**: 🎉 Following up on PixelHacker, our latest AI Image Inpainting work, [Moebius](https://github.com/hustvl/Moebius), has been accepted by ECCV'26. We challenge the "scale-at-all-costs" path dependency dictated by the Scaling Law narrative and provide a core insight into breaking the impossible triangle of "low parameters, fast inference, and high quality".

* **`June 01, 2026`**: 📰✨ The journal version of PixelHacker is coming soon. Stay tuned! ☕ Next, we will gradually update the README and project page.

* **`May 20, 2025`**: 🔥 We have released the [code](https://github.com/hustvl/PixelHacker) and [weights](https://huggingface.co/hustvl/PixelHacker/tree/main). The weights include the pretrained and all fine-tuned versions, each only 0.8B params. Feel free to play!

* **`May 5, 2025`**: 🎉 PixelHacker has achieved the No. 1 daily ranking on [Hugging Face](https://huggingface.co/papers/date/2025-05-05)!

* **`May 1, 2025`**: 🔥 We have released the [project page](https://hustvl.github.io/PixelHacker) with 63+ demos on natural and portrait scenes. Have fun! 🤗

* **`April 30, 2025`:** 🔥 We have released the [arXiv paper](https://arxiv.org/abs/2504.20438) for PixelHacker. The code and project page will be released soon.

## 🏕️ Performance on Natural Scene

<div align="center">
<img src="./assets/Demo1.gif" width="360px"></img>
</div>

<img src="./assets/Cover.png"></img>

<img src="./assets/Natural-Scene.png"></img>

## 🤗 Performance on Portrait Scene
<div align="center">
<img src="./assets/Demo2.gif" width="360px"></img>
</div>

<img src="./assets/Human-Face.png"></img>

## 📦 Environment Setups
* torch 2.3.0
* transformers 4.40.0
* diffusers 0.30.2
* See 'requirements.txt' for detailed Python libraries required

```shell
conda create -n pixelhacker python=3.10
conda activate pixelhacker
# cd /xx/xx/PixelHacker
pip install -r requirements.txt
```

## 🗃️ Model Checkpoints
* Download the checkpoint of [VAE](https://huggingface.co/hustvl/PixelHacker/tree/main/vae) and put it into ../PixelHacker/vae.

* Download the checkpoints of [pretrained version](https://huggingface.co/hustvl/PixelHacker/tree/main/pretrained), [fine-tuned version (places2)](https://huggingface.co/hustvl/PixelHacker/tree/main/ft_places2), [fine-tuned version (celeba-hq)](https://huggingface.co/hustvl/PixelHacker/tree/main/ft_celebahq), [fine-tuned version (ffhq)](https://huggingface.co/hustvl/PixelHacker/tree/main/ft_ffhq), and put them into ../PixelHacker/weight.

* Finally, the detailed organizational form is as follows:
```shell
├── PixelHacker
│    ├── weight
│        ├── pretrained
│            ├── diffusion_pytorch_model.bin
│        ├── ft_places2
│            ├── diffusion_pytorch_model.bin
│        ├── ft_celebahq
│            ├── diffusion_pytorch_model.bin
│        ├── ft_ffhq
│            ├── diffusion_pytorch_model.bin
│    ├── vae
│        ├── config.json
│        ├── diffusion_pytorch_model.bin
│    ├── ...
```

## 🔮 Inference
You can run the following code directly to get the inpainting result of the example image-mask pair, and the result will be generated in ../PixelHacker/outputs. If you want to infer on custom data, just place the image and mask with the same name in ../PixelHacker/imgs and ../PixelHacker/masks, respectively, then run the following code as well.
```shell
python infer_pixelhacker.py \
--config config/PixelHacker_sdvae_f8d4.yaml \
--weight weight/ft_places/diffusion_pytorch_model.bin
```


## 🎓 Citation

```shell
@misc{xu2025pixelhacker,
      title={PixelHacker: Image Inpainting with Structural and Semantic Consistency}, 
      author={Ziyang Xu and Kangsheng Duan and Xiaolei Shen and Zhifeng Ding and Wenyu Liu and Xiaohu Ruan and Xiaoxin Chen and Xinggang Wang},
      year={2025},
      eprint={2504.20438},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2504.20438}, 
}
```
