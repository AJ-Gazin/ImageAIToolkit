[English](README.md) | [简体中文](README_zh_cn.md)

<!-- ## **Hunyuan3D-1.0** -->



- [x] Inference 
- [x] Checkpoints
- [x] Baking


#### Installation Guide for Linux

We provide an env_install.sh script file for setting up environment. 

```
conda create -n hunyuan3d-1 python=3.9 or 3.10 or 3.11 or 3.12
conda activate hunyuan3d-1

pip3 install torch torchvision --index-url https://download.pytorch.org/whl/cu121
bash env_install.sh

# or
pip3 install -r requirements.txt --index-url https://download.pytorch.org/whl/cu121
pip3 install git+https://github.com/facebookresearch/pytorch3d@stable
pip3 install git+https://github.com/NVlabs/nvdiffrast
```

dust3r baking install:

```
cd third_party
git clone --recursive https://github.com/naver/dust3r.git

cd ../third_party/weights
wget https://download.europe.naverlabs.com/ComputerVision/DUSt3R/DUSt3R_ViTLarge_BaseDecoder_512_dpt.pth

```


#### Download Pretrained Models

The models are available at [https://huggingface.co/tencent/Hunyuan3D-1](https://huggingface.co/tencent/Hunyuan3D-1):

+ `Hunyuan3D-1/lite`, lite model for multi-view generation.
+ `Hunyuan3D-1/std`, standard model for multi-view generation.
+ `Hunyuan3D-1/svrm`, sparse-view reconstruction model.


To download the model, first install the huggingface-cli. (Detailed instructions are available [here](https://huggingface.co/docs/huggingface_hub/guides/cli).)

```shell
mkdir weights
huggingface-cli download tencent/Hunyuan3D-1 --local-dir ./weights

mkdir weights/hunyuanDiT
huggingface-cli download Tencent-Hunyuan/HunyuanDiT-v1.1-Diffusers-Distilled --local-dir ./weights/hunyuanDiT
```


